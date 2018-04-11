# Laravel Excel v2.1.* for Laravel 5

> This is a forked version to fix the issue of failure to parse cells that are being formatted as date but contain non-date data. [Please checkout the "bugfix" branch, branching out from the original 2.1.27 branch] 

[<img src="http://www.maatwebsite.nl/img/excel_banner.jpg"/>](https://laravel-excel.maatwebsite.nl/)
[<img src="https://cloud.githubusercontent.com/assets/7728097/6332170/1b495af2-bb84-11e4-9a93-34a9abc01840.jpg"/>](http://www.maatwebsite.nl/vacature-php-programmeur-maastricht)

Laravel Excel brings the power of PHPOffice's PHPExcel to Laravel 5 with a touch of the Laravel Magic. It includes features like: importing Excel and CSV to collections, exporting models, array's and views to Excel, importing batches of files and importing a file by a config file.

- Import into Laravel **Collections**
- Export **Blade views** to Excel and CSV with optional CSS styling
- **Batch** imports
- A lot of optional **config settings**
- Easy **cell caching**
- Chunked and queued importer
- ExcelFile method injections
- Editing existing Excel files
- **Advanced import** by config files
- and many more...

---

```php
Excel::create('Laravel Excel', function($excel) {

    $excel->sheet('Excel sheet', function($sheet) {

        $sheet->setOrientation('landscape');

    });

})->export('xls');
```

---

[![Build Status](https://travis-ci.org/Maatwebsite/Laravel-Excel.svg?branch=master)](https://travis-ci.org/Maatwebsite/Laravel-Excel)
[![Latest Stable Version](https://poser.pugx.org/maatwebsite/excel/v/stable.png)](https://packagist.org/packages/maatwebsite/excel) [![Total Downloads](https://poser.pugx.org/maatwebsite/excel/downloads.png)](https://packagist.org/packages/maatwebsite/excel)  [![License](https://poser.pugx.org/maatwebsite/excel/license.png)](https://packagist.org/packages/maatwebsite/excel)
[![Monthly Downloads](https://poser.pugx.org/maatwebsite/excel/d/monthly.png)](https://packagist.org/packages/maatwebsite/excel)
[![Daily Downloads](https://poser.pugx.org/maatwebsite/excel/d/daily.png)](https://packagist.org/packages/maatwebsite/excel)

# Installation

As this is a forked version, to add this package into your application, edit your `composer.json` file, then run `composer install` if it is a new install, or `composer update maatwebsite/excel` if you are trying to update your existing package from the original creator.

```
{
    ...

    "require": {
        "maatwebsite/excel": "dev-bugfix"
    },

    "repositories": [
        {
            "type": "vcs",
            "url": "https://github.com/simmatrix/Laravel-Excel"
        }
    ]

    ...
}
```

In Laravel 5.5 or higher, this package will be automatically discovered and you can safely skip the following two steps.

If using Laravel 5.4 or lower, after updating composer, add the ServiceProvider to the providers array in `config/app.php`

```php
Maatwebsite\Excel\ExcelServiceProvider::class,
```

You can use the facade for shorter code; if using Laravel 5.4 or lower, add this to your aliases:

```php
'Excel' => Maatwebsite\Excel\Facades\Excel::class,
```

The class is bound to the ioC as `excel`

```php
$excel = App::make('excel');
```

To publish the config settings in Laravel 5 use:

```php
php artisan vendor:publish --provider="Maatwebsite\Excel\ExcelServiceProvider"
```

This will add an `excel.php` config file to your config folder.

# Documentation

The complete documentation can be found at: [https://laravel-excel.maatwebsite.nl/docs](https://laravel-excel.maatwebsite.nl/docs)

# Support

Support only through Github. Please don't mail us about issues, make a Github issue instead.

# Contributing

**ALL** bug fixes should be made to appropriate branch (e.g. `2.0` for 2.0.* bug fixes). Bug fixes should never be sent to the `master` branch.

More about contributing can be found at: [https://laravel-excel.maatwebsite.nl/docs/2.1/getting-started/contributing](https://laravel-excel.maatwebsite.nl/docs/2.1/getting-started/contributing)

# License

This package is licensed under MIT. You are free to use it in personal and commercial projects. The code can be forked and modified, but the original copyright author should always be included!

# FAQ

1) Chunk importer only imports the first row

Check that auto_detect_line_endings in your php.ini is set to true.
