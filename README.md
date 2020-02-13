# Add Yaml file support for Laravel 5.2 Configuration

This package uses Symfony/Yaml parser.

## Installing

Add ```"vunh00/yaml-configuration": "3.1.*"``` to your **composer.json** by running :

```
php composer.phar require vunh00/yaml-configuration
```

And select version : ```3.1.*```

## Add support in Laravel

You have to add (or merge)

```php
protected function bootstrappers()
{
    $this->bootstrappers[] = 'Vunh00\Core\Config\LoadYamlConfiguration';
    return $this->bootstrappers;
}
```

to your **app/Http/Kernel.php** and/or **app/Console/Kernel.php**.

## How to use

Just use regular **php** files or use **yml** or **yaml** files instead.

**PHP** :

```php
<?php

return [
    'debug' => false,
    'key'   => 'foobar',
];
```

Will be equivalent to :

**YAML**

```yaml
debug: false
key: foobar
```

## Use functions

You can use any php functions like that :

```yaml
routes_file: %app_path%/routes.php
unit_test: %base_path:behat.yml%
something: %sprintf:hell %s,world%
```

Enjoy it ! Feel free to fork :) !

This package is fork of devitek/yaml-configuration
