# php trim 中的坑

```php
    echo ltrim("Hello World", "Hdle");
    // 输出:  o World
```

<!-- more -->

解析:
 > 把2个参数中的字符转换成数组,
 然后遍历参数1中的每个字符,
 如果在第二个参数数组中就去掉,否则终止;
 
```php
$str='Hello World';
$mask='Hdle';
echo ltrim($str, $mask); // o World
echo "\r\n";
$args1 = str_split($str);
$args2 = str_split($mask);
foreach ($args1 as $key => $value) {
	if (in_array($value, $args2)) {
		unset($args1[$key]);
	}else{
		break;
	}
}
echo implode($args1); // o World
```



