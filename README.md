MailGun Extension for Yii 2
===============================

This extension provides a [MailGun](http://www.mailgun.com/) mail solution for [Yii framework 2.0](http://www.yiiframework.com).

For license information check the [LICENSE](LICENSE.md)-file.

Installation
------------

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```
php composer.phar require --prefer-dist bsadnu/yii2-mailgunmailer "*"
```

or add

```json
"bsadnu/yii2-mailgunmailer": "*"
```

to the require section of your composer.json.

Usage
-----

To use this extension,  simply add the following code in your application configuration:

```php
'components' => [
    ...
    'mailer' => [
        'class' => 'bsadnu\mailgunmailer\Mailer',
        'key' => 'key-example',
        'domain' => 'mg.example.com',
    ],
    ...
],
```

You can then send an email as follows:

```php
Yii::$app->mailer->compose('contact/html', ['contactForm' => $form])
    ->setFrom('from@domain.com')
    ->setTo($form->email)
    ->setSubject($form->subject)
    ->send();
```
