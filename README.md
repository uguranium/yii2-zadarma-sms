# Zadarma Sms Api for Yii2

Yii2 extension for work with Zadarma API. Allows to work with API methods.

[![Latest Stable Version](https://poser.pugx.org/uguranyum/yii2-zadarma-sms/v/stable.png)](https://packagist.org/packages/uguranyum/yii2-zadarma-sms)
[![Total Downloads](https://poser.pugx.org/uguranyum/yii2-zadarma-sms/downloads.png)](https://packagist.org/packages/uguranyum/yii2-zadarma-sms)


##Requirements
- Yii2 PHP Framework
- PHP >= 5.3.0
- cURL

##DOWNLOAD VIA COMPOSER
```
composer require uguranyum/yii2-zadarma-sms
```

##How to use

Before the using controller please define Zadarma class
```
use uguranyum\zadarma\Zadarma;
```
#### For sending Sms

```
$params = [
    'number' => 'YOUR PHONE NUMBER',
    'message' => 'PLEASE WRITE YOUR MESSAGE HERE',
];

$zadarma    = new Zadarma("ZADARMA API KEY", "ZADARMA API SECRET");
$answer     = $zadarma->call('/v1/sms/send/', $params, 'post');
$answerObject = json_decode($answer);
print_r($answerObject);
```
#### For looking statics

```
$params = array(
    'start' => '2015-01-01 00:00:00',
    'end' => '2015-01-31 00:00:00',
    /*'sip' => 'YOURSIP',*/
    /*'cost_only' => true,*/
    /*'type' => 'toll'*/
);
$zadarma    = new \Zadarma_API\Client(KEY, SECRET);
$answer     = $zadarma->call('/v1/statistics/', $params);
$answerObject = json_decode($answer);
```
