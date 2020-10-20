# 注意  
php >=5.0
# 地址  
https://packagist.org/packages/devilhot/des

# 安装方法  
composer require devilhot/des

# 使用方法  
```
<?php
include_once './vendor/autoload.php';

use Devil\Des;

//$iv = bin2hex(openssl_random_pseudo_bytes(4)); 可随机
$iv = 'abc12345';//只能是8位字符串
$key = 'a123456';
$arr = ['id'=>1,'name'=>'ceshi','title'=>'haha'];
$val = json_encode($arr,JSON_UNESCAPED_UNICODE);



// DES CBC 加解密（安全，速度慢）
$des = new Des($key, 'DES-CBC', Des::OUTPUT_BASE64,$iv);
echo $base64Sign = $des->encrypt($val);
echo "\n";
echo $des->decrypt($base64Sign);
echo "\n";

// DES CBC 加解密（安全，速度慢）
$des = new Des($key, 'DES-CBC', Des::OUTPUT_HEX,$iv);
echo $base64Sign = $des->encrypt($val);
echo "\n";
echo $des->decrypt($base64Sign);
echo "\n";


// DES ECB 加解密 （不安全，速度快，易破解）
$des = new Des($key, 'DES-ECB', Des::OUTPUT_BASE64);
echo $base64Sign = $des->encrypt($val);
echo "\n";
echo $des->decrypt($base64Sign);
echo "\n";

// DES ECB 加解密 （不安全，速度快，易破解）
$des = new Des($key, 'DES-ECB', Des::OUTPUT_HEX);
echo $base64Sign = $des->encrypt($val);
echo "\n";
echo $des->decrypt($base64Sign);
echo "\n";
```
