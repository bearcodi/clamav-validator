# ClamAV Validator For Laravel 5

[![SensioLabsInsight](https://insight.sensiolabs.com/projects/80f28825-1385-4daa-aaad-0e4c6b6b3910/mini.png)](https://insight.sensiolabs.com/projects/80f28825-1385-4daa-aaad-0e4c6b6b3910)
[![Code Coverage](https://scrutinizer-ci.com/g/sunspikes/clamav-validator/badges/coverage.png?b=master)](https://scrutinizer-ci.com/g/sunspikes/clamav-validator/?branch=master)
[![Code Quality](https://scrutinizer-ci.com/g/sunspikes/clamav-validator/badges/quality-score.png?b=master)](https://scrutinizer-ci.com/g/sunspikes/clamav-validator)
[![Build Status](https://travis-ci.org/sunspikes/clamav-validator.svg?branch=master)](https://travis-ci.org/sunspikes/clamav-validator) 
[![Latest Stable Version](https://poser.pugx.org/sunspikes/clamav-validator/v/stable)](https://packagist.org/packages/sunspikes/clamav-validator)
[![License](https://poser.pugx.org/sunspikes/clamav-validator/license)](https://packagist.org/packages/sunspikes/clamav-validator)

Custom Laravel 5 anti-virus validator for file uploads.

* [Requirements](#requirements)
* [Installation](#installation)
* [Usage](#usage)
* [Author](#author)

<a name="requirements"></a> 
## Requirements

You must have ClamAV anti-virus scanner running on the server to make this package work.

You can see the ClamAV installation instructions on the official [ClamAV documentation](http://www.clamav.net/documents/installing-clamav).

For example on an Ubuntu machine, you can do:

```sh
# Install clamav virus scanner
sudo apt-get update
sudo apt-get install clamav-daemon

# Update virus definitions
sudo freshclam

# Start the scanner service
sudo service clamav-daemon start
```

This package is not tested on windows, but if you have ClamAV running (usually on port 3310) it should work.

<a name="installation"></a>
## Installation

Install the package through [Composer](http://getcomposer.org).

Run `composer require sunspikes/clamav-validator`

Add the following to your `providers` array in `config/app.php`:

```php
'providers' => array(
	// ...

	Sunspikes\ClamavValidator\ClamavValidatorServiceProvider::class,
),
```

<a name="usage"></a>
## Usage

Use it like any `Validator` rule:

```php
$rules = array(
	'my_file_field' => 'clamav',
);
```

<a name="author"></a>
## Author

Krishnaprasad MG [@sunspikes]

_Contact me at [sunspikes at gmail dot com]_
