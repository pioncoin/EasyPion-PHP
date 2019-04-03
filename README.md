# EasyPion-PHP
By Pioncore
https://github.com/pioncore/EasyPion-PHP

A simple class for making calls to Pion's RPC API using PHP.

## Getting Started:
1. Include easypion.php into your PHP script:

	`require_once('easypion.php');`
2. Initialize Pion connection/object:

	`$pion = new \pioncoin\EasyPion('username','password');`

	Optionally, you can specify a host, port. Default is HTTP on localhost port 9953.

	`$pion = new \pioncoin\EasyPion('username','password','localhost','9953');`

	If you wish to make an SSL connection you can set an optional CA certificate or leave blank
	`$pion->setSSL('/full/path/to/mycertificate.cert');`

3. Make calls to piond as methods for your object. Examples:

	`$pion->getinfo();`
	`$pion->getrawtransaction('be1bf890e0fbfcac38092a1a654b2e472d7a64c15cda04b706494f4087e8305b',1);`
	`$pion->getblock('000000000027169cc7e9b2f1541f1b822151e4981f51288ccfa83e575a42150c');`
	`$pion->mnbudget('show');`

## Additional Info:
* When a call fails for any reason, it will return false and put the error message in $pion->error

* The HTTP status code can be found in $pion->status and will either be a valid HTTP status code or will be 0 if cURL was unable to connect.

* The full response (not usually needed) is stored in $pion->response while the raw JSON is stored in $pion->raw_response

## Contribution Info

This is forked from EasyDash-PHP by Alexandre Devilliers (https://github.com/elbereth/EasyDash-PHP).
Original code is licenced under MIT.
