# full-text-search
## Getting Started
Install full text search via Composer

Note: If you do not have Composer yet, you can install it by following the instructions on https://getcomposer.org

# Step 1. Install package
````
composer require kashif/full-text-search
````
after installing this package, include FullTextSearch Trail in your model
so a scope is now available called 'search',
then add folowing code in your model.

```php
protected $searchable = [
    'title', 'name', 'email'
];
```

Then when you want to apply full text search on specific model, do something like below. 

```php
User::search('john')->get();
```

####Note: Full text search with fulltext indexing by make apply fields indexing. so you can add indexes like below.
```php
ALTER TABLE`users` ADD FULLTEXT search(name, email);
```

After this full text search should work.
