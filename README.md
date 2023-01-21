# docker-php-dev-container

This repository provides a development environment for WHMCS or WordPress

# Configure it for WordPress development
We will be using [Docker binding mount](https://docs.docker.com/storage/bind-mounts/) to get WordPress files readable by [Intelephense](https://marketplace.visualstudio.com/items?itemName =bmewburn.vscode-intelephense-client). In this way we get the autocompletion of WordPress functions.

1. First, download https://wordpress.org/latest.zip on your host machine.
2. Look in the `devcontainer.json`, put the path where you unzipped WordPress in the `mounts.source` key.
     1. If you want to change the path in `mounts.target`, change it also in `settings.json` and `intelephense.environment.includePaths`
3. Then you need to tell php-cs-fixer to use `.php-cs-fixer-wp.php`. Then, open `devcontainer.json` and edit the `php-cs-fixer.config` key. You can delete the other `.php-cs-fixer.php`.
4. Delete `.git` and start your own repository.
5. Install the VS Code [Dev Containers] extension (https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers).
6. Place your files and start configuring in `/src`.
7. Press CTRL + P and select Rebuild Container.
8. Finally, start coding.

# How to change PHP version
1. In `.devcontainer/devcontainer.json`, the `image:` key refers to the PHP image version. You must change this to change the PHP version of the container.

2. Also in `devcontainer.json`, set the PHP version for the Intelephense suggestions in the `intelephense.environment.phpVersion` key.
