# amazon-s3-for-seph
Modified for Using with CEPH

based by AWS SDK for PHP - Version 1

[aws/aws-sdk-php]: https://github.com/aws/aws-sdk-php

```php
$Connection = new AmazonS3(array(
    'key' => $config['key'],
    'secret' => $config['secret'],
    'canonical_name' => $config['canonical_name'],
));
$Connection->set_hostname($this->_config['hostname']);
$Connection->disable_ssl();
$Connection->allow_hostname_override(false);
$Connection->enable_path_style(true);
$Connection->path_style = true;
$Connection->debug_mode = false;


$Connection->create_object('bucket', 'file_path', array(
    'body' => 'data',
    'contentType' => 'set mime type'
));

$Connection->if_object_exists('bucket', 'file_path');

// there be save file
$tmp = tempnam("/tmp", "diz");
$Connection->get_object('bucket', 'file_path', array(
    'fileDownload' => $tmp,
));

$Connection->delete_object('bucket', 'file_path');
```
