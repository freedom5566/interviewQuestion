# 以下七題挑三題寫
1. 用 PHP 實作一個計算 Fibonacci number (https://en.wikipedia.org/wiki/Fibonacci_number) 的 Function例如： fib(6) 的結果為 8請用 Recursive 及 非 Recursive 的方式各作一次

*Recursive*
```php
<?php

//遞迴費氏數列函式
function Fib($num){
    if ($num==1 || $num==2) {
        return 1;
    }
    else {
        return (Fib($num-1)+Fib($num-2));
    }
}


for ($i=1; $i < 10; $i++) {
    echo "Fib($i)=".Fib($i)."\n";
}

?>
```
*非Recursive*
```php
<?php

//非遞迴費氏數列函式
function Fib($num){
    $sum=0;
    $pre=0;
    $fi=1;
    for ($i=1; $i<$num ; $i++) {
        $sum=$pre+$fi;
        $pre=$fi;
        $fi=$sum;
    }
    return $fi;

}

for ($i=1; $i < 10; $i++) {
    echo "Fib($i)=".Fib($i)."\n";
}

?>
```


2. 給定一個 PHP array, 例如：data = [ 10, 20, 50, 7, 9, ];寫一個函數計算該 array 的中位數。

```php
$arr = Array(10, 20, 50, 7, 9);

//偶數
if (count($arr)%2==0) {

    echo "中位數是:".($arr[floor((count($arr)-1)/2)]+$arr[floor((count($arr)-1)/2+1)])/2;

}

//奇數
else {

    $keys = array_keys($arr);
    echo "中位數是:".$arr[$keys[round(count($keys)/2)-1]];

}
?>
```

3. 如何用 PHP 指令產生：   
    1. 昨天下午3:00 的 timestamp   
    2. 上星期二早上8:00 的 timestamp2016/11/11    
    3. 早上 10:30 的 timestamp

```php
<?php
date_default_timezone_set('asia/taipei');
$d = new Datetime("now");

// 昨天下午3:00 的 timestamp

    echo $d->modify("-1 day 15:00")->format("Y-m-d A:H:i")."\n";
    echo strtotime("-1 day 15:00")."\n";

// 上星期二早上8:00 的 timestamp

    echo $d->modify("-1 week last Tuesday 8:00")->format("Y-m-d A:H:i")."\n";
    echo strtotime("-1 week last Tuesday 8:00")."\n";

// 2016/11/11 早上10:30 的 timestamp

    echo $d->modify("2016/11/11 10:30")->format("Y-m-d A:H:i")."\n";
    echo strtotime("2016/11/11 10:30");

?>
```

4. 在 Web application 的環境下，請問 Cookie 功用是什麼？請列舉一個例子說明之

5. 請說明 HTTP/2 和 HTTP/1.1 有何不同？HTTP/2 最主要是要改善什麼問題並簡單描述 HTTP/2 是怎麼達到這個目的

6. 在資料庫中，Primary key、Unique key、Foreign key有什麼不同？並描述在什麼情況下應該要使用什麼key。

7. 在資料庫中，ACID分別代表什麼意思？如果不符合ACID會造成什麼問題？

***

嗯，程式對我來說比較簡單，所以挑前3個寫，後面4題之後來看看，雖然被發無聲卡了QQ
