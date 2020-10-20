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

$key = 'a123456';
$arr = ['id'=>1,'name'=>'ceshi','title'=>'haha'];
$val = json_encode($arr,JSON_UNESCAPED_UNICODE);

//快捷用法(默认使用CBC模式，IV初始化向量随机)
$des = new Des($key);
echo $base64Sign = $des->encrypt($val);
echo "\n";
echo $des->decrypt($base64Sign);
echo "\n";


// DES CBC 加解密（安全，速度慢）
$des = new Des($key, 'DES-CBC', Des::OUTPUT_BASE64);
echo $base64Sign = $des->encrypt($val);
echo "\n";
echo $des->decrypt($base64Sign);
echo "\n";

// DES CBC 加解密（安全，速度慢）
$des = new Des($key, 'DES-CBC', Des::OUTPUT_HEX);
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
