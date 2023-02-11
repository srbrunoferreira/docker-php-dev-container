# docker-php-dev-container

This repository provides a simple and fast env setup for WHMCS or WordPress

Use this to develop your WHMCS module or gateway.

Use this to code your WordPress plugin.

# Features
* PHP linting and formatting with Intelephense and php-cs-fixer
* JavaScript linting and formatting with ESlint and Standard style
* WordPress autocompletion with Intelephense

# Setups

First, you need to install the following items:
* [Dev Container](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) extension in VS Code.
* [Docker Desktop](https://www.docker.com/products/docker-desktop/)

## For WordPress development

1. In devcontainer.json, change the key `php-cs-fixer.config` to `.php-cs-fixer-wp.php` and then delete the file `php-cs-fixer.php`.

2. Make sure that in `devcontainer.json` the key `intelephense.stubs` has "WordPress" in its value.
3. Remove unecessary configs for WordPress development such as:
   1. `aswinkumar863.smarty-template-support` in devcontainer.json
4. Delete `.git` and start your own repository.
5. Place your files in `/src`.
6. Press CTRL + Shift + P and select Rebuild Container Without.
7. Finally, start coding.

## For WHMCS development
1. In devcontainer.json, change the key `php-cs-fixer.config` to `.php-cs-fixer.php` and then delete the file `php-cs-fixer-wp.php`.
2. Remove "WordPres" stub from `devcontainer.json` -> `intelephense.stubs`.
3. Place your files in `/src`.
4. Press CTRL + Shift + P and select Rebuild Container Without.
5. Finally, start coding.

### Recommended extensions

Take a look at `extensions.json` and search these extensions in VS Code markteplace.

# How to change PHP version
1. In `.devcontainer/devcontainer.json`, the `image:` key refers to the PHP image version. You must change this to change the PHP version of the container.

2. Also in `devcontainer.json`, set the PHP version for the Intelephense suggestions in the `intelephense.environment.phpVersion` key.
