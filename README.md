# GroupDocs.Conversion Cloud SDK for PHP
This repository contains GroupDocs.Conversion Cloud SDK for PHP source code. This SDK allows you to work with GroupDocs.Conversion Cloud REST APIs in your PHP applications.

## Dependencies
- PHP 5.5 or later

## Authorization
To use SDK you need AppSID and AppKey authorization keys. You can your AppSID and AppKey at https://dashboard.groupdocs.cloud (free registration is required).  

## Installation & Usage
### Composer

The package is available at [Packagist](https://packagist.org/) and it can be installed via [Composer](http://getcomposer.org/) by executing following command:
```
composer require groupdocscloud/conversion-sdk-php
``` 

Or you can install SDK via [Composer](http://getcomposer.org/) directly from this repository, add the following to `composer.json`:

```
{
  "repositories": [
    {
      "type": "git",
      "url": "https://github.com/groupdocs-conversion-cloud/groupdocs-conversion-cloud-php.git"
    }
  ],
  "require": {
    "groupdocscloud/conversion-sdk-php": "*"
  }
}
```

Then run `composer install`

### Manual Installation

Clone or download this repository, then run `composer install` in the root directory to install dependencies and include `autoload.php` into your code file:

```php
require_once('/path/to/groupdocs-conversion-cloud-php/vendor/autoload.php');
```

## Tests

To run the unit tests set your AppSID and AppKey in [json.config](tests/GroupDocs/Conversion/config.json) and execute following commands:

```
composer install
./vendor/bin/phpunit
```

## Getting Started
Please follow the [installation procedure](#installation--usage) and then run the following:

```php
<?php

require_once(__DIR__ . '/vendor/autoload.php');

//TODO: Get your AppSID and AppKey at https://dashboard.groupdocs.cloud (free registration is required).
$configuration = new GroupDocs\Conversion\Configuration();
$configuration->setAppSid("XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX");
$configuration->setAppKey("XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX");

$conversionApi = new GroupDocs\Conversion\ConversionApi($configuration); 

try {
    $request = new GroupDocs\Conversion\Model\Requests\GetAllPossibleConversionsRequest();
    $response = $conversionApi->getAllPossibleConversions($request);

    foreach ($response->getConversions() as $key => $conversion) {
        echo $conversion->getSourceFileType() . " - " .  join(",", $conversion->getPossibleConversions()) . "\n";
    }
} catch (Exception $e) {
    echo  "Something went wrong: ",  $e->getMessage(), "\n";
    PHP_EOL;
}

?>
```

## Licensing
GroupDocs.Conversion for Cloud SDK for PHP is licensed under [MIT License](LICENSE).

## Resources
+ [**Website**](https://www.groupdocs.cloud)
+ [**Product Home**](https://products.groupdocs.cloud/conversion/cloud)
+ [**Documentation**](https://docs.groupdocs.cloud/display/conversioncloud/Home)
+ [**Free Support Forum**](https://forum.groupdocs.cloud/c/conversion)
+ [**Blog**](https://blog.groupdocs.cloud/category/groupdocs-conversion-cloud-product-family)

## Contact Us
Your feedback is very important to us. Please feel free to contact us using our [Support Forums](https://forum.groupdocs.cloud/c/conversion).
