# Dick Settings

[![Latest Version on Packagist][ico-version]][link-packagist]
[![Software License][ico-license]](LICENSE.md)
[![Build Status][ico-travis]][link-travis]
[![Coverage Status][ico-scrutinizer]][link-scrutinizer]
[![Quality Score][ico-code-quality]][link-code-quality]
[![Total Downloads][ico-downloads]][link-downloads]

An interface for the administrator to easily change application settings. Uses Dick CRUD, on Laravel 5.1.

## Install

Via Composer

``` bash
$ composer require dick/settings
$ php artisan vendor:publish --provider="Dick\Settings\SettingsServiceProvider"
$ php artisan migrate
```

## Usage

### End user
Add it to the menu or access it by its route: **application/admin/setting**

### Programmer
Use it like you would any config value in a virtual settings.php file. Except the values are stored in the database and fetched on boot, instead of being stored in a file.

``` php
Config::get('settings.contact_email')
```

### Add new settings

Settings are stored in the database in the "settings" table. Its columns are:
- id (ex: 1)
- key (ex: contact_email)
- name (ex: Contact form email address)
- description (ex: The email address that all emails go to.)
- value (ex: admin@usedick.com)
- field (Dick CRUD field configuration in JSON format. http://usedick.com/docs)
- active (1 or 0)
- created_at
- updated_at

There is no interface available to add new settings. They are added by the developer directly in the database, since the Dick CRUD field configuration is a bit complicated. See the field types and their configuration code on http://usedick.com/docs

## Screenshots

See http://usedick.com

## Change log

Please see [CHANGELOG](CHANGELOG.md) for more information what has changed recently.

## Testing

``` bash
$ composer test
```

## Contributing

Please see [CONTRIBUTING](CONTRIBUTING.md) for details.

## Security

If you discover any security related issues, please email hello@tabacitu.ro instead of using the issue tracker.

## Credits

- [Cristian Tabacitu][link-author]
- [All Contributors][link-contributors]

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.

[ico-version]: https://img.shields.io/packagist/v/dick/settings.svg?style=flat-square
[ico-license]: https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square
[ico-travis]: https://img.shields.io/travis/tabacitu/settings/master.svg?style=flat-square
[ico-scrutinizer]: https://img.shields.io/scrutinizer/coverage/g/tabacitu/settings.svg?style=flat-square
[ico-code-quality]: https://img.shields.io/scrutinizer/g/tabacitu/settings.svg?style=flat-square
[ico-downloads]: https://img.shields.io/packagist/dt/dick/settings.svg?style=flat-square

[link-packagist]: https://packagist.org/packages/dick/settings
[link-travis]: https://travis-ci.org/tabacitu/settings
[link-scrutinizer]: https://scrutinizer-ci.com/g/tabacitu/settings/code-structure
[link-code-quality]: https://scrutinizer-ci.com/g/tabacitu/settings
[link-downloads]: https://packagist.org/packages/dick/settings
[link-author]: https://github.com/tabacitu
[link-contributors]: ../../contributors
