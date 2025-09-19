# DDEV based Local development stack

## Setting up

1. Clone this repo, enter the folder.
2. Install DDEV if not already done: https://ddev.readthedocs.io/en/stable/#installation
3. `ddev start`
4. If needed, change Drupal version in composer.json
5. `ddev composer install`
7. `ddev composer clean-install`


## Local development & QA

--

## Running automated tests and code analysis tools for modules

1. `ddev ssh`
2. `mkdir web/sites/default/files/simpletest/browser_output`
   (if not already done)
3. `composer test [module_name]` (the module folder must be in 
   web/modules/contrib)
4. `composer phpstan [module_name]` (the module folder must be in 
   web/modules/contrib)
5. `composer phpcs [module_name]` (the module folder must be in 
   web/modules/contrib)
