# PHP Travis Client

It is simple PHP implementation of client using [travisci api](http://about.travis-ci.org/docs/dev/api/).

[![Build Status](https://secure.travis-ci.org/l3l0/php-travis-client.png?branch=master)](http://travis-ci.org/l3l0/php-travis-client)

## Installation

Download repository then [download composer](http://getcomposer.org/doc/01-basic-usage)
using `wget -nc http://getcomposer.org/composer.phar`

So install command will look like `php composer.phar install`

## Usage

Just look at tests :P . Basic example:

```php
<?php

require_once 'vendor/.composer/autoload.php';

$client = new Travis\Client();

$repository = $client->fetchRepository('l3l0/OpenSocialBundle');

echo $repository->getId() . "\n";
echo $repository->getSlug() . "\n";
echo $repository->getLastBuild()->getId() . "\n";
echo $repository->getBuilds()->findOneBy(array('number' => 2))->getId() . "\n";

echo 'Builds:' . "\n";
foreach ($repository->getBuilds() as $build) {
    echo "\t" . $build->getId() . "\n";
}
```
