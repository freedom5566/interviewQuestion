1. 觀念題類

```javascript
let a="10";
let b="20";
let c="30";

console.log(a-b+c); // -1030
console.log(a-b&c); // 22
```

這題原來考的是[二進制](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_Operators "mdn")......

蠻多這些題目，我一直以為這類的在C語言裏面才有，對我來說這也算是一個盲點吧

2. 1-2+3-4...+n

```javascript
"use strict";
function sum(m) {

    let num = 0;
    for (let a = 1; a <= m; a++) {
        if (a % 2 === 1) {
            num += a;
        }
        else {
            num -= a;
        }

    }
    return num;


}

console.log(sum(10));
```

3. 型態觀念題

<table>
    <tr>
        <td>資料型態</td>
        <td>位元組</td>
        <td>範圍</td>
    </tr>
    <tr>
        <td>long int</td>
        <td>4</td>
        <td>-2147483648到2147483648</td>
    </tr>
    <tr>
    <td>int</td>
    <td>4</td>
    <td>-2147483648到2147483648</td>    
    </tr>
    <tr>
    <td>short int</td>
    <td>2</td>
    <td>-32768到32768</td>    
    </tr>
    <tr>
    <td>char</td>
    <td>1</td>
    <td>0到256</td>    
    </tr>
    <tr>
    <td>float</td>
    <td>4</td>
    <td>1.2e-38到3.4e38</td>    
    </tr>
    <tr>
    <td>double</td>
    <td>8</td>
    <td>2.2e-308到1.8e308</td>    
    </tr>
    <tr>
    <td>unsigned long int</td>
    <td>4</td>
    <td>0到4294967295</td>    
    </tr>
    <tr>
    <td>unsigned int</td>
    <td>4</td>
    <td>0到4294967295</td>    
    </tr>
    <tr>
    <td>unsigned short int</td>
    <td>4</td>
    <td>0到655535</td>    
    </tr>
</table>

明明是php考題居然會有這個......，回來看一下php文件，只有`boolen`、`integer`、`float aka double`、`string`，我是不是被唬爛了阿......?

4. PHP連線sql撈資料的問題(填充程式碼)

這題我有點忘了，題目裏面的連線是用MySQL extension(php5之後棄用)......想說誰還用這個？，回家查了一下，主流除了PDO以外，還能使用MySQL`i` extension，也算是長知識了。（注意多了一個`i`，這個PHP7還能用）        

5. 氣泡排序法
```javascript
"use strict";
let Bubblesort=(arr)=>{
    
    for(let i=0;i<arr.length-1;i++){
        for(let j=0;j<arr.length-1-i;j++){
            if(arr[j]>arr[j+1]){
        
                let temp=arr[j];
                arr[j]=arr[j+1];
                arr[j+1]=temp;

            }
        }
    }

    return arr;
};

let num=[30,70,50,7,1,9,40];
let num2=[1,57,568,56,85,84,8,58,53,86];

//方法一
Bubblesort(num);
console.log(num);
//方法二
console.log(num2.sort((i,j)=>i-j));//mdn這招超酷
```
方法二[mdn](https://developer.mozilla.org/zh-TW/docs/Web/JavaScript/Reference/Global_Objects/Array/sort "sort")     

       
6. 字串反轉

```javascript
"use strict";

//方法一
let s="Hello World";

console.log(s.split("").reverse().join(""));

//方法二
let rev=(rr)=>{
    //let len=rr.length;
    //console.log(len);
    let temp=new Array(rr.length);
    
    for(let i=rr.length-1;i>=0;i--){
        
        temp[i]=rr.charAt(i);
        process.stdout.write(temp[i]);//不換行print
        
    }

}
rev(s);
```
7. 以下PHP陣列最後會顯示甚麼
```php
<?php

$arr=["Alan Mathison Turing","Dwayne Douglas Johnson 24y7usd","Stephen William Hawking3/14"];
echo current($arr)."\n"; // 當前指針
echo reset($arr)."\n"; // 重設指針，回到第一個
echo next($arr)."\n"; // 指向下一個
echo current($arr)."\n";
echo reset($arr);

?>
```
還是第一個

***

無聲卡，也算是有增加經驗
