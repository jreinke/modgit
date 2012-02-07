# Deploy Git modules with include/exclude features

*modgit* is an alternative to the excellent [modman tool](http://code.google.com/p/module-manager/). Directly inspired from it, *modgit* allows you to deploy Git modules physically in your project (no symlinks). Additionaly, you can define include/exclude filters to deploy only files and folders of your choice.

## Requirements

* bash
* git

## Installation

### curl installation
* curl https://raw.github.com/jreinke/modgit/master/modgit > modgit
* chmod +x modgit
* sudo mv /usr/local/bin

### wget installation
* wget -O modgit https://raw.github.com/jreinke/modgit/master/modgit
* chmod +x modgit
* sudo mv modgit /usr/local/bin

### Manual download
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

Include filter with custom target:

    $ modgit -i lib:library clone elastica git://github.com/ruflin/Elastica.git

Exclude filter:

    $ modgit -e modman -e README.md -e LICENSE.txt clone mage-phpunit https://github.com/IvanChepurnyi/EcomDev_PHPUnit.git

Automatic modman compatibility (parse remote modman file for files and folders mapping):

    $ modgit clone magneto-debug https://github.com/madalinoprea/magneto-debug.git

Git options:

    $ modgit clone elastica https://github.com/ruflin/Elastica.git --branch gh-pages

## Coming soon

* Add dry-run option
