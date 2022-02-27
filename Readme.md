#BItCoin
A simple class for making calls to Bitcoin's API using PHP.
font : https://github.com/aceat64/EasyBitcoin-PHP
## Utilização 

Initialize Bitcoin connection/object
```php

use Adewebcombr\JsonRpc\BitCoin;
$bitcoin = new Bitcoin('username','password');



//Optionally, you can specify a host and port.
$bitcoin = new Bitcoin('username','password','host','port');
// Defaults are:
//	host = localhost
//	port = 8332
//	proto = http

// If you wish to make an SSL connection you can set an optional CA certificate or leave blank
// This will set the protocol to HTTPS and some CURL flags
$bitcoin->setSSL('/full/path/to/mycertificate.cert');

// Make calls to bitcoind as methods for your object. Responses are returned as an array.
// Examples:
$bitcoin->getinfo();
$bitcoin->getrawtransaction('0e3e2357e806b6cdb1f70b54c3a3a17b6714ee1f0e68bebb44a74b1efd512098',1);
$bitcoin->getblock('000000000019d6689c085ae165831e934ff763ae46a2a6c172b3f1b60a8ce26f');

// The full response (not usually needed) is stored in $this->response
// while the raw JSON is stored in $this->raw_response

// When a call fails for any reason, it will return FALSE and put the error message in $this->error
// Example:
echo $bitcoin->error;

// The HTTP status code can be found in $this->status and will either be a valid HTTP status code
// or will be 0 if cURL was unable to connect.
// Example:
echo $bitcoin->status;

## Requisitos
PHP 7.0 >
