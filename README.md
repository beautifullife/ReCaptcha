# ReCaptcha plugin for CakePHP 3.x

## Notice

You can install this plugin into your CakePHP application using [composer](http://getcomposer.org).

The recommended way to install composer packages is:

```
composer require beautifullife/recaptcha
```

## Requirements

Register an account at: https://www.google.com/recaptcha/admin

## Installation

Using command line to install vendor (required)

```
cd ReCaptcha
composer install
```

## Configs

Adding this code for 'config/bootstrap.php':

```
Plugin::load('ReCaptcha', ['bootstrap' => false, 'routes' => true]);
```

Modify file 'ReCaptcha\src\Controller':

```
const SECRET = 'your_secret_code';
```

On your app Controller, add these codes:

```
use ReCaptcha\Controller\ReCaptchaController;
...
$verifyRecaptcha = ReCaptchaController::verify();
if ($verifyRecaptcha) {
    //verify user success
} else {
    //verify user fail
}
```

## In Template

```
<?php

$siteKey = 'your_secret_code';
$lang = 'en';

?>

<script type="text/javascript" src="https://www.google.com/recaptcha/api.js?hl=<?php echo $lang; ?>"></script>
<div class="g-recaptcha" data-sitekey="<?= $siteKey ?>"></div>
```

## Author

Dung Nguyen

## Websites

sheetmusic4you.net

vietnamcoffeeplace.com

saledream.com