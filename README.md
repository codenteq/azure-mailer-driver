# Microsoft Azure Mailer Driver

[![Latest Stable Version](http://poser.pugx.org/codenteq/azure-mailer-driver/v)](https://packagist.org/packages/codenteq/azure-mailer-driver)
[![Total Downloads](http://poser.pugx.org/codenteq/azure-mailer-driver/downloads)](https://packagist.org/packages/codenteq/azure-mailer-driver)
[![License](http://poser.pugx.org/codenteq/azure-mailer-driver/license)](https://github.com/codenteq/azure-mailer-driver/blob/master/LICENSE)

## 1. Introduction:

The integration of Microsoft Azure ACS for Symfony Mailer provides a simple and clean email API supported by the [Symfony Azure Mailer Bridge](https://github.com/symfony/azure-mailer) component.

## 2. Requirements

* **PHP**: 8.1 or higher.
* **Composer**: 1.6.5 or higher.

## 3. Installation

First time using Azure ECS? Create your [Azure account](https://azure.com), if you don’t have one already.

- Run the following command
```bash
composer require codenteq/azure-mailer-driver
```

### Set mail config

> WARNING <br>
> It will check existence of the `config/mail.php` file, if it exists then please update the file manually with the below details.

```php
'mailers' => [
        'azure' => [
            'transport'             => 'azure',
            'resource_name'         => env('AZURE_MAIL_RESOURCE_NAME'),
            'endpoint'              => env('AZURE_MAIL_ENDPOINT', 'https://my-acs-resource-name.communication.azure.com'),
            'access_key'            => env('AZURE_MAIL_KEY'),
            'api_version'           => env('AZURE_MAIL_API_VERSION', '2023-03-31'),
            'disable_user_tracking' => env('AZURE_MAIL_DISABLE_TRACKING', false),
            'client' => [
                'max_host_connections' => 10,
                'max_pending_pushes' => 100,
            ]
        ],
```

> WARNING <br>
> It will check existence of the .env file, if it exists then please update the file manually with the below details.  

```bash 
  # Mail service entries... 
  MAIL_MAILER=azure
  
  # Azure Service entries
  AZURE_MAIL_RESOURCE_NAME=my-acs-resource-name
  # AZURE_MAIL_ENDPOINT= #optional
  AZURE_MAIL_KEY=Base64AzureAccessToken
  # AZURE_MAIL_API_VERSION=2023-03-31 #optional
  # AZURE_MAIL_DISABLE_TRACKING=false #optional
  
```

> just sent your notification mail messages!

## Available resources

| Resource             | Status   |
| -------------------- | :------: |
| Plain Text           | ✅  |
| HTML                 | ✅  |
| Attachments          | ✅  |
| Multiple recipients  | ✅  |
| Auth HMAC-SHA256     | ✅  |
| Notifications        | ✅  |
| Mkt Campaigns        | ✅  |
| Markdown             | ✅  |

## How to contribute
Azure Mailer Driver is always open for direct contributions. Contributions can be in the form of design suggestions, documentation improvements, new component suggestions, code improvements, adding new features or fixing problems. For more information please check our [Contribution Guideline document.](https://github.com/codenteq/azure-mailer-driver/blob/master/CONTRIBUTING.md)