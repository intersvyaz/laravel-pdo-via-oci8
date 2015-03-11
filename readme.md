# PDO Userspace Driver for Oracle (oci8)

### Is a fork of [yajra/laravel-pdo-via-oci8](https://github.com/yajra/laravel-pdo-via-oci8)
Optimized and tested for Yii.

Changes:
- Default behavior $dsn parameter on Oci8::__construct.

Correct $dsn value: ```oci:dbname=DB_NAME;charser=AL32UTF8``` not: ```DB_NAME```.
- Separate blob and clob.

Use ```Oci8::PARAM_BLOB``` and ```Oci8::PARAM_CLOB``` constant in bindValue.
- Automatic save blob fields.

```php
Yii::app()->db->createCommand("INSERT INTO table (data) VALUES (empty_blob()) returning data into :data")
->bindParam(':data', 'very very long string', Oci8::PARAM_BLOB)
->execute();
```

###PDO via Oci8

[![Latest Stable Version](https://poser.pugx.org/yajra/laravel-pdo-via-oci8/v/stable.png)](https://packagist.org/packages/yajra/laravel-pdo-via-oci8) [![Total Downloads](https://poser.pugx.org/yajra/laravel-pdo-via-oci8/downloads.png)](https://packagist.org/packages/yajra/laravel-pdo-via-oci8) [![Build Status](https://travis-ci.org/yajra/laravel-pdo-via-oci8.png)](https://travis-ci.org/yajra/laravel-pdo-via-oci8)

The [yajra/laravel-pdo-via-oci8](https://github.com/yajra/laravel-pdo-via-oci8) package is a simple userspace driver for PDO that uses the tried and
tested [OCI8](http://php.net/oci8) functions instead of using the still experimental and not all that functionnal
[PDO_OCI](http://www.php.net/manual/en/ref.pdo-oci.php) library.

**Please report any bugs you may find.**

- [Installation](#installation)
- [Credits](#credits)

###Installation

Add `yajra/laravel-pdo-via-oci8` as a requirement to composer.json:

```json
{
    "require": {
        "yajra/laravel-pdo-via-oci8": "~0.9"
    }
}
```
And then run `composer update`

***Note:***
lastInsertId function returns the current value of the sequence related to the table where record is inserted.
The sequence name should follow this format ```{$table}.'_'.{$column}.'_seq'``` for it to work properly.



###Credits

- [crazycodr/pdo-via-oci8](https://github.com/crazycodr/pdo-via-oci8)
