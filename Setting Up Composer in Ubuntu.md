# Download PHP

If from development repositories, download php using:

```sh
sudo apt install php
```

Programatically installing composer can be done using the following script:

```sh
#!/bin/sh

EXPECTED_CHECKSUM="$(php -r 'copy("https://composer.github.io/installer.sig", "php://stdout");')"
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
ACTUAL_CHECKSUM="$(php -r "echo hash_file('sha384', 'composer-setup.php');")"

if [ "$EXPECTED_CHECKSUM" != "$ACTUAL_CHECKSUM" ]
then
    >&2 echo 'ERROR: Invalid installer checksum'
    rm composer-setup.php
    exit 1
fi

php composer-setup.php --quiet
RESULT=$?
rm composer-setup.php
exit $RESULT
```

Save this file somewhere as `php-install-composer.sh`. Running this file will produce a script called `composer.phar` which we can move to a directory under `PATH` for execution. Example:

```sh
sudo mv composer.phar /usr/local/bin/composer
```

Verify that `composer` is working by running:

```sh
composer --version
```