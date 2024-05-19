# LPD

Laravel Package Developer is a new No Starting Kit Laravel 11 application with a Packages
directory specifically for developing Laravel packages.

## Usage

### Important Note
Note to self and anyone else. Do not run composer install or update without first cloning in an actual package and 
setting up the repositories section and requiring the package in composer.json.
Read notes below!

How it works:
app/Packages/.gitignore ensures the Packages directory stays but anything inside it is 
ignored by the LPD repository. So you can git clone an existing package into this directory.

Next cd into your newly cloned package and run composer install to install dependencies
in the package. As you make changes to the package it's self, you can run git commands
from within the package and it should not affect the parent repository.

For now, in order to test/use the package in the parent Laravel application you just need
to add the repositories section to the base applications composer.json and require the
package. Then be sure to cd back to the base application directory and run composer update.
This will install the local package into the laravel application.

I want to look into ways of automating so I don't need to manually update the composer
file. For now this works but when I commit changes to the laravel application repository
the composer.json file will be setup for this specific package. I'll probably create a
setup or configure script similar to the one in the spatie skeleton that will edit the
composer file. This way LPD can be cloned, run setup, and use over and over without 
having to manually edit composer.json every time.


