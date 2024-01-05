Via `composer`, we can create a new Laravel project using the following command:

```sh
composer create-project laravel/laravel [projectname]
```

To run the development server (defaults to port `8000`):

```sh
php artisan serve
```

Running in a different port:

```sh
php artisan serve --port 3000
```
### Common Errors

#### Platform Dependencies (Ubuntu)

**Error Message**:
```
Your requirements could not be resolved to an installable set of packages.

  Problem 1
    - laravel/pint[v1.0.0, ..., v1.13.6] require ext-xml * -> it is missing from your system. Install or enable PHP's xml extension.
    - Root composer.json requires laravel/pint ^1.0 -> satisfiable by laravel/pint[v1.0.0, ..., v1.13.6].

To enable extensions, verify that they are enabled in your .ini files:
    - /etc/php/8.2/cli/php.ini
    - /etc/php/8.2/cli/conf.d/10-opcache.ini
    - /etc/php/8.2/cli/conf.d/10-pdo.ini
    - /etc/php/8.2/cli/conf.d/20-calendar.ini
    - /etc/php/8.2/cli/conf.d/20-ctype.ini
    - /etc/php/8.2/cli/conf.d/20-exif.ini
    - /etc/php/8.2/cli/conf.d/20-ffi.ini
    - /etc/php/8.2/cli/conf.d/20-fileinfo.ini
    - /etc/php/8.2/cli/conf.d/20-ftp.ini
    - /etc/php/8.2/cli/conf.d/20-gettext.ini
    - /etc/php/8.2/cli/conf.d/20-iconv.ini
    - /etc/php/8.2/cli/conf.d/20-phar.ini
    - /etc/php/8.2/cli/conf.d/20-posix.ini
    - /etc/php/8.2/cli/conf.d/20-readline.ini
    - /etc/php/8.2/cli/conf.d/20-shmop.ini
    - /etc/php/8.2/cli/conf.d/20-sockets.ini
    - /etc/php/8.2/cli/conf.d/20-sysvmsg.ini
    - /etc/php/8.2/cli/conf.d/20-sysvsem.ini
    - /etc/php/8.2/cli/conf.d/20-sysvshm.ini
    - /etc/php/8.2/cli/conf.d/20-tokenizer.ini
You can also run `php --ini` in a terminal to see which files are used by PHP in CLI mode.
Alternatively, you can run Composer with `--ignore-platform-req=ext-xml` to temporarily ignore these required extensions.
```

**Solution**

Install Ubuntu dependencies:

```sh
sudo apt install php-curl php-gd php-xml
```
