
Composer Plugin for php-build
=============================

## What is this?

This small script hooks into [php-build](https://github.com/CHH/php-build) 
and automatically installs [Composer](http://getcomposer.org/) on each Build,
so you don't have to.

## What is it good for?

Ideal for using [Composer and their awesome features](http://getcomposer.org)
with multiple PHP Versions. The idea comes from
[CHH's phpunit plugin](https://github.com/CHH/php-build-plugin-phpunit).

Before, I had to install Composer globally on my machine or on each PHP Build
I wanted to have Composer avaliable. Now, using this plugin, everytime you
build a new PHP version with `php-build`, the `composer` command will be ready
to go.

## Install

It's up to you: use the [`install.sh`](https://raw.github.com/rogeriopradoj/php-build-plugin-composer/master/install.sh) script, or make installation by hand.

### Install via `install.sh`

    $ wget -O install.sh http://git.io/Hqr8pQ || curl -o install.sh http://git.io/Hqr8pQ && ./install.sh

If necessary, `install.sh` can receive an environment variable `PREFIX`, to use
in case of your php-build is installed in a directory different than `/usr/local/`. E.g.:
    
    $ PREFIX=/path_to_another_directory ./install.sh


### Install by hand

**First of all**, download the plugin (e.g. to your home directory, `~`):

- Either via `wget`:

        $ cd ~
        $ rm -rf php-build-plugin-composer-master master.tar.gz
        $ wget https://github.com/rogeriopradoj/php-build-plugin-composer/archive/master.tar.gz
        $ tar -vzxf master.tar.gz

- Or via `curl`:

        $ cd ~
        $ rm -rf php-build-plugin-composer-master master.tar.gz
        $ curl -LO https://github.com/rogeriopradoj/php-build-plugin-composer/archive/master.tar.gz
        $ tar -vzxf master.tar.gz

- Or via `git clone`:

        $ cd ~ 
        $ rm -rf php-build-plugin-composer-master master.tar.gz
        $ git clone https://github.com/rogeriopradoj/php-build-plugin-composer.git php-build-plugin-composer-master

**Secondly**, ensure that the `composer.sh` in `share/php-build/after-install.d/` is
executable, e.g.:

    $ cd ~/php-build-plugin-composer-master
    $ chmod +x share/php-build/after-install.d/composer.sh

**Finally**, copy the `share` directory into your `php-build` installation, or
link `share/php-build/after-install.d/composer.sh` to
`share/php-build/after-install.d/` in your `php-build` installation.

- Copying way

        $ cd ~/php-build-plugin-composer-master
        $ cp -r share /usr/local

- Linking way
        
        $ cd /usr/local/share/php-build/after-install.d
        $ ln -s ~/php-build-plugin-composer-master/share/php-build/after-install.d/composer.sh

*Note 1:* Both examples above are supposing you have installed
`php-build` in default location, `/usr/local`. If not, change accordingly.

*Note 2:* If you don't have permissions to write to that directory, run
the commands as superuser, either via `su -c` or via `sudo`.

## Changelog

### 1.0.0 - 2013-12-29

- Self update composer.phar if it is already is TMP.
- Create `CONTRIBUTE.md` and [How to contribute](#how-to-contribute) section.

### 0.0.2 - 2013-05-12

- Includes `install.sh` script.

### 0.0.1 - 2013-03-14

- First release.

## How to contribute

Please see [CONTRIBUTE.md](CONTRIBUTE.md).

[![Bitdeli Badge](https://d2weczhvl823v0.cloudfront.net/rogeriopradoj/php-build-plugin-composer/trend.png)](https://bitdeli.com/free "Bitdeli Badge")

