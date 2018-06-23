# Laravel Scout Elasticsearch Driver

[![Software License](https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square)](LICENSE.md)

This is the [Elasticsearch](https://www.elastic.co/products/elasticsearch) driver for Laravel Scout with multiple indexes support.

Package is based on tamayo/laravel-scout-elastic, and created to replace [depeceated](https://www.elastic.co/guide/en/elasticsearch/reference/master/removal-of-types.html) types, with [Index per document type](https://www.elastic.co/guide/en/elasticsearch/reference/master/removal-of-types.html#_index_per_document_type) solution.

## Contents

- [Installation](#installation)
- [Usage](#usage)
- [Credits](#credits)
- [License](#license)

## Installation

``` bash
composer require sl0wik/laravel-scout-elasticsearch-driver
```

Add the Scout service provider and the package service provider in your app.php config:

```php
// config/app.php
'providers' => [
    ...
    Laravel\Scout\ScoutServiceProvider::class,
    ...
    ScoutEngines\Elasticsearch\ElasticsearchProvider::class,
],
```

### Setting up Elasticsearch configuration

After you've published the Laravel Scout package configuration update config/scout.php:

```php
    'driver' => env('SCOUT_DRIVER', 'elasticsearch'),
...
    'elasticsearch' => [
        'hosts' => [
            env('ELASTICSEARCH_HOST', 'http://localhost'),
        ],
    ],
...
```

## Usage

Now you can use Laravel Scout as described in the [official documentation](https://laravel.com/docs/5.4/scout)

## Credits

- [Erick Tamayo](https://github.com/ericktamayo) and [Contributors](https://github.com/ErickTamayo/laravel-scout-elastic/contributors)
- [Michael Slowik](https://github.com/sl0wik)

## License

The MIT License (MIT).
