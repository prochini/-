### 練習一：好多星星 

```js
請寫出一個 function stars，接收一個參數 n，並且按照規律印出相對應的圖案。

stars(1) 預期輸出：
*

stars(3) 預期輸出：

*
**
***
stars(7) 預期輸出：

*
**
***
****
*****
******
*******
```
 

```js
let counter = '';
function stars(n) {
  for (let i = 1; i <= n; i += 1) {
    counter += '*';
    console.log(counter);
  }
}
stars(7);
```
### 練習二：好多星星 回傳版
請寫出一個 function makeStars，接收一個參數 n，並且根據規律「回傳」字串

makeStars(1) 正確回傳值：*

makeStars(2) 正確回傳值：*\n**

makeStars(5) 正確回傳值：\n**\n**\n****\n*****

```js
let total ='';
function makeStars(n){
        for (let i = 1; i <= n; i++){
        star(i)
        total += (i!== n ? '/n':'')
        
    }
    return total
}
function star(n){
    for (let i = 1; i <= n; i++){
        total += "*"
    }
}
console.log(makeStars(7))
```
### 練習三：好多星星 加強版

```js
請寫出一個函式 stars2，接收一個參數 n，並依照規律印出圖形。

stars2(1) 預期輸出：
*

stars2(3) 預期輸出：

*
**
***
**
*
stars2(5) 預期輸出：

*
**
***
****
*****
****
***
**
*
```


```js
let sum ='';
function stars2(n){
    for (let i =1; i <= n; i+=1){
        sum += '*'
        console.log(sum)        
    }for (let j = n-1; j > 0; j-=1){
        let sub = sum.slice(0,j);
        console.log(sub)
    }
}
stars2(20)
```
### 練習四：乘法表
請寫一個函式 table，接收一個數字 n，印出 n1 ~ n9 的結果。

table(7) 預期輸出：
7 *1 = 1
7 *2 = 14
7 *3 = 21
7 *4 = 28
7 *5 = 35
7 *6 = 42
7 *7 = 49
7 *8 = 56
7 *9 = 63

```js
function table (n){
    for (let i = 1; i < 10; i+=1) {
        let times =n+'*' + i +' = '+ n * i;
        console.log(times)
    }    
}
table (7)
```
### 練習五：九九乘法表
練習五：九九乘法表
請寫出一個 function table9to9，並列出 11 ~ 99。

table9to9() 預期輸出：

11 = 1
12 = 2
13 = 3
.....
51 = 5
52 = 10
53 = 15
....
97 = 63
98 = 72
9*9 = 81

```js
function table9to9 (){
    let times ;
    for (let n = 1; n < 10; n+=1){
        for (let i = 1; i < 10; i+=1) {
            times =n+'*' + i +' = '+ n * i;
            console.log(times)
        }       
    }
}
table9to9 ()
```
### 練習六：費式數列
費式數列的定義為：第 n 個數等於前兩個數的總和，因此這個數列會長的像這樣：1 1 2 3 5 8 13 21 ....

用比較數學一點的講法，就是：

fib(0) = 0
fib(1) = 1
for n >=2, fib(n) = fib(n-1) + fib(n-2)

現在，請你寫出一個 fib 的函式，回傳位在第 n 個位置的數字

fib(1) 預期回傳值：1

fib(2) 預期回傳值：1

fib(8) 預期回傳值：21

```js
function fib(n){
    var fib =[0,1]
for (var i =2 ;i <= n;i++){
fib[i] = fib[i-1]+fib[i-2]
}
return fib[n]
}
console.log(fib(7))
```
### 練習七：字串反轉
請寫出一個函式 reverse，接收一個字串，並且回傳反轉過後的字串。（禁止使用內建函式 reverse）

reverse("abcd") 預期回傳值：dcba

reverse("12345aa") 預期回傳值：aa54321

```js
function reverse(n){
    let sum = '';                           //宣告 sum 來儲存排序出來的，字串的值
    for (var i =n.length ;i >=0 ;i-=1){     //i 為字串長度，字串的最後一個字；i 大於 0 ;i 遞減;4-3-2-1-0
    sum += n.charAt(i)                      //sum = sum + n 字串的第4位數 ,第3位數,第2位數,第1位數
}
return sum                                  //回傳sum
}
    console.log(reverse("abcd"))

```
### 練習八：大小寫互換
請寫一個函式 swap，接收一個字串，並且回傳大小寫互換後的字串。

swap("Peter") 預期回傳值：pETER

swap("AbCdE") 預期回傳值：aBcDe

```js
function  swap(n){
    let sum ='';                        //累加字串
    for (let i=0 ;i<n.length;i++){      //迴圈跑i從0開始累加1到字串長度
        let num = n.charAt(i);          //設定字串的第i個字母
        if ('A'<=num&&num<='Z'){        //確認第1個字母是否為大寫，是的話就轉為小寫，不是就往下跑
            sum += num.toLowerCase()    //是的話就放入累加字串
        }else if ('a'<=num&&num<='z') { //確認第1個字母是否為小寫，是的話就轉為大寫，(此必為小寫)
            sum += num.toUpperCase()    //放入累加字串
        }
    }

    return sum                          //回傳完成累加的字串
}
console.log(swap('pETER'))
```
### 練習九：找出最小值
請寫出一個函式 findMin，接收一個陣列並回傳陣列中的最小值。（禁止使用內建函式 sort）

findMin([1, 2, 5, 6, 99, 4, 5]) 預期回傳值：1

findMin([1, 6, 0, 33, 44, 88, -10]) 預期回傳值：-10

```js
function findMin(ary){
    let min = ary[0];                       //宣告min: 假設第一個值為最小值，會定期更新的數
    for(let i =1; i<ary.length; i++) {      //讓 i 從1跑到尾，從陣列第1個數跑到最後1個數
        if(min>ary[i]){                     //若是第i數小於min
            min = ary[i];                   //讓min等於第i數，更新最小值
    }
}        
   return min                               //回傳得到的最小值
    }       

console.log(findMin([5,6,99,4,5,5,4,5,6]))

```
### 練習十：找出第 n 小的值
這題是上一題的加強版，上一題只要你找出最小值，而這一題請你寫一個 function findNthMin，接收一個陣列以及一個數字 n，找出第 n 小的數字。（禁止使用內建函式 sort）

提示：假設我要找出第 2 小的值，我只要先找出最小的值然後再把它刪掉，再重新找一次最小的值，就會是第 2 小的值了。

findNthMin([1, 2, 3, 4, 5], 1) 預期回傳值：1

findNthMin([1, 3, 5, 7, 9], 3) 預期回傳值：5

findNthMin([1, 1, 1, 1, 1], 2) 預期回傳值：1

```js
function findMin(ary){
    let min = ary[0]; 
    let minIndex =0;
            for(let i =1; i<ary.length; i++) {      
            if(min>ary[i]){                     
                min = ary[i];
                minIndex =i             
        }        
    }        
   return minIndex                               
    } 
function findMinth(ary,nth){
        for (let i=1 ;i<nth; i++){
            let minIndex =findMin(ary);
            ary.splice(minIndex,1)
        }
        let realMinIndex =findMin(ary)
        return ary[realMinIndex]
    }
console.log(findMinth([1, 30, 50, 70, 9], 3))
```
