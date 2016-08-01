# README #

This is a OrientDB driver for Laravel 5.2

### Requirements ###

* PHP >= 5.5.9
* Laravel 5.2
* OrientDB 2.2 or above

### Installation ###

Add the package to your `composer.json`:

```

"repositories": [
    {
        "type": "vcs",
        "url": "https://github.com/lequocnam/orient-laravel.gitt"
    }
],
"require": {
    ...
    "lequocnam/orient-laravel": "dev-master"
},
```
Run `composer update` to install this package.

Then, add the service provider in `config/app.php`:


```

/*
 * Application Service Providers...
 */

...
Lequocnam\Orient\OrientServiceProvider::class,
```


### Database configuration ###

Open config/database.php make `orientdb` your default connection:

```

'default' => 'orientdb',
'default_nosql' => 'orientdb', //optional
...
'connections' => [
    'orientdb' => [
        'driver' => 'orientdb',
        'host'   => 'localhost',
        'port'   => '2424',
        'database' => 'database_name',
        'username' => 'root',
        'password' => 'root'
    ]
]
```

### How to use ###
In your model:

```

<?php

namespace App;

use Lequocnam\Orient\Eloquent\Model;
use Lequocnam\Orient\Eloquent\SoftDeletes;

class Animal extends Model
{
    use SoftDeletes;

    ...
}

```


### Current Features ###

* Basic CRUD similar Eloquent Model
* SoftDeletes

### Upcomming Features ###

* Support Transaction
* Relationships (HasOne, HasMany, BelongsTo, ...)
* Prevent SQL Injection
