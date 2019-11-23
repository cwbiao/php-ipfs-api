IPFS API wrapper library in PHP
======================================

> A client library for the IPFS API.

-----
[![Codacy Badge](https://api.codacy.com/project/badge/Grade/b402bd7a7ae4452db5262493413a933d)](https://www.codacy.com/manual/rannmann/php-ipfs-api?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=rannmann/php-ipfs-api&amp;utm_campaign=Badge_Grade)
[![CodeFactor](https://www.codefactor.io/repository/github/rannmann/php-ipfs-api/badge/master)](https://www.codefactor.io/repository/github/rannmann/php-ipfs-api/overview/master)


# Usage

## Installing 

This library requires the cURL module:

```bash
$ sudo apt-get install php5-curl
$ composer require rannmann/php-ipfs-api
$ composer install
```

```PHP
use Cloutier\PhpIpfsApi\IPFS;

// connect to ipfs daemon API server
$ipfs = new IPFS("localhost", "8080", "5001"); // leaving out the arguments will default to these values
```


## API


#### add

Adds content to IPFS. 

**Usage**
```PHP
$hash = $ipfs->add("Hello world");
```

#### addFromPath

Adds content to IPFS from a filename (helper method)

**Usage**
```PHP
$hash = $ipfs->addFromPath("myFile.txt");
```


#### get

Retrieves the contents of a single hash.

**Usage**
```PHP
$ipfs->get($hash);
```

#### ls
Gets the node structure of a hash.

**Usage**
```PHP
$obj = $ipfs->ls($hash);

foreach ($obj as $e) {
	echo $e['Hash'];
	echo $e['Size'];
	echo $e['Name'];
}
```


#### Object size

Returns object size.

**Usage**
```PHP
$size = $ipfs->size($hash);
```

#### Pin

Pin or unpin a hash.

**Usage**
```PHP
$ipfs->pinAdd($hash);
$ipfs->pinRm($hash);
```

#### Pin

Get information about your ipfs node.

**Usage**
```PHP
print_r($ipfs->id());
```

# License 

The MIT License (MIT)

Copyright (c) 2015-2016 Vincent Cloutier  
Copyright (c) 2016 S3r3nity Technologies 

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
