## This is just PHP 5.5 compatible fork of [pascaldevink/shortuuid](https://github.com/pascaldevink/shortuuid)
*If you are on PHP 5.6+, use the [original source](https://github.com/pascaldevink/shortuuid).*

```shortuuid``` is a simple php library that generates concise, unambiguous, URL-safe UUIDs.

Often, one needs to use non-sequential IDs in places where users will see them, but the IDs must be as concise and easy 
to use as possible. shortuuid solves this problem by translating generated uuids to base57 using lowercase and uppercase 
letters and digits, and removing similar-looking characters such as l, 1, I, O and 0.

This library is a port of it's python counter-part by Stochastic Technologies: https://github.com/stochastic-technologies/shortuuid

[![Build Status](https://travis-ci.org/ondram/shortuuid.svg?branch=master)](https://travis-ci.org/ondram/shortuuid)

# Installation

The preferred method of installation is via [Packagist](https://packagist.org/) and [Composer](https://getcomposer.org). 
Run the following command to install the package and add it as a requirement to your project's composer.json:
```
composer require ondram/shortuuid-php55
```

# Examples
```php
<?php
require 'vendor/autoload.php';

use Ramsey\Uuid\Uuid;
use PascalDeVink\ShortUuid\ShortUuid;

$uuid = Uuid::fromString('4e52c919-513e-4562-9248-7dd612c6c1ca');
$shortUuid = new ShortUuid();
echo $shortUuid->encode($uuid); // output fpfyRTmt6XeE9ehEKZ5LwF
```

```php
<?php
require 'vendor/autoload.php';

use PascalDeVink\ShortUuid\ShortUuid;

$shortUuid = new ShortUuid();
echo $shortUuid->decode('fpfyRTmt6XeE9ehEKZ5LwF'); // outputs 4e52c919-513e-4562-9248-7dd612c6c1ca
```
