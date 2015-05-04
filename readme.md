# PDO Userspace Driver for Oracle (oci8)

[![Latest Stable Version](https://poser.pugx.org/intersvyaz/pdo-oci8/v/stable)](https://packagist.org/packages/intersvyaz/pdo-oci8)
[![Total Downloads](https://poser.pugx.org/intersvyaz/pdo-oci8/downloads)](https://packagist.org/packages/intersvyaz/pdo-oci8)
[![License](https://poser.pugx.org/intersvyaz/pdo-oci8/license)](https://packagist.org/packages/intersvyaz/pdo-oci8)

This package is a simple userspace driver for PDO that uses the tried and tested [OCI8](http://php.net/oci8) functions instead of using the still experimental and not all that functionnal [PDO_OCI](http://www.php.net/manual/en/ref.pdo-oci.php) library.

**Please report any bugs you may find.**

## Features

### Automatic save blob fields.

Use ```Oci8::PARAM_BLOB``` and ```Oci8::PARAM_CLOB``` constant in bindValue.

```php
Yii::app()->db->createCommand("INSERT INTO table (data) VALUES (empty_blob()) returning data into :data")
->bindParam(':data', 'very very long string', Oci8::PARAM_BLOB)
->execute();
```

##Installation

Run `php composer.phar require "intersvyaz/pdo-oci8: ~2.0.0"`
or add as a requirement to composer.json:

```json
{
    "require": {
        "intersvyaz/pdo-oci8": "~2.0.0"
    }
}
```
And then run `composer update`

###Credits

- [crazycodr/pdo-via-oci8](https://github.com/crazycodr/pdo-via-oci8)
- [yajra/laravel-pdo-via-oci8](https://github.com/yajra/laravel-pdo-via-oci8)
