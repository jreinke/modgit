# Deploy Git modules with include/exclude features

*modgit* is an alternative to the excellent [modman tool](http://code.google.com/p/module-manager/). Directly inspired from it, *modgit* allows you to deploy Git modules physically in your project (no symlinks). Additionaly, you can define include/exclude filters to deploy only files and folders of your choice.

## Requirements

* bash
* git

## Installation

* Download shell script from [download page](https://github.com/jreinke/modgit/downloads)
* Copy modgit file to `/usr/local/bin` (or any folder in your $PATH)
* Performs `chmod +x modgit`

## Usage

Install a module:

    $ cd /my/project/path
    $ modgit init
    $ modgit clone <module> <git_repository>

Update a module:

    $ modgit update <module>

Update all modules:

    $ modgit update-all

Remove a module:

    $ modgit remove <module>

List installed modules:

    $ modgit list

## Advanced usage

Include filter:

    $ modgit -i lib/ clone elastica git://github.com/ruflin/Elastica.git

Exclude filter:

    $ modgit -e modman -e README.md -e LICENSE.txt clone mage-phpunit https://github.com/IvanChepurnyi/EcomDev_PHPUnit.git

## TODO

* Add custom options to git clone command
* Add dry-run option

## 