# CakePHP IPFinder Library
The official CodeIgniter IPFinder Library for the [IPFinder.io](https://ipfinder.io) get details for :
-  IP address details
-  ASN  details
-  Firewall details
-  IP Address Ranges details
-  Domain details
-  Domain history details
-  Domain list details
-  TOKEN details


## Installation
The recommended way to install composer packages is:

```bash
$ composer require ipfinder-io/cakephp-ipfinder
```

## How to Use

###  Enable Plugin

```php
// src/Application.php

public function bootstrap()
{
    $this->addPlugin('IPFinderCakePHP');
}
```

Before of CakePHP 3.7

```php
Plugin::load('IPFinderCakePHP', ['routes' => true]);
```

### Create a TestsController in CakePHP  using the below command line

```bash
$ php bin/cake bake controller Tests
```

### load the IPFinder library with use

```php
use IPFinderCakePHP\Controller\IpfinderController as ipfinderio;
```
### example
Create an empty index.ctp file in /src/Template/Tests folder.

```php
<?php

namespace App\Controller;

use App\Controller\AppController;
use IPFinderCakePHP\Controller\IpfinderController as ipfinderio;

class TestsController extends AppController
{
    /**
     * Index method
     *
     */
    public function index()
    {
        $ipfinder = new ipfinderio();

        echo "<pre>";
        var_dump($ipfinder->Authentication());
        echo "<pre>";
    }
}
```

## List methods

| Name             |  Description
| ---------------  | ----------- |
| Authentication   | Get details for an Your IP address.
| getAddressInfo   | Get details for an IP address. e.x(`1.1.1.1`)
| getAsn           | Get details for an AS number.  e.x(`AS1`)
| getStatus        | Get details for an API Token .
| getRanges        | Get details for an Organization name. e.x(`Telecom Algeria`)
| getFirewall      | Get Firewall data e.x(`AS1`,`nginx_deny`)
| getDomain        | Get Domain IP e.x(`google.com`)
| getDomainHistory | Get Domain IP history e.x(`google.com`)
| getDomainBy      | Get list Domain By ASN, Country,Ranges e.x(`DZ,FR`)



## other

- See the [IPFidner documentation](https://ipfinder.io/docs).
- See the [IPFinder PHP Client Library](https://github.com/ipfinder-io/ip-finder-php).

[![GitHub license](https://img.shields.io/github.com/ipfinder-io/cakephp-ipfinder.svg)](https://github.com/ipfinder-io/cakephp-ipfinder/blob/master/LICENSE)
