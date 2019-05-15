

### 練習一：排序
請寫一個 function sort，接收一個陣列並且回傳由小到大排序後的陣列。（禁止使用內建函式 sort）

提示：如果你已經會找第 n 小的值了，試著把這個概念應用到這題上。

sort([ 6, 8, 3, 2]) 預期回傳值：[2, 3, 6, 8]

sort([ 1, 2, 7 ,5]) 預期回傳值：[1, 2, 5, 7]
```js
function findMin(ary){  //排序 :找出最小值
    let min = ary[0]; 
    let minIndex =0;
            for(let i =1; i<ary.length; i++) {      
            if(min>ary[i]){                     
                min = ary[i];
                minIndex =i                //最小值得位置
        }        
    }        
   return minIndex                         //回傳到function sort
    } 
function sort(ary){
    let length = ary.length               //儲存陣列長度
    let result =[];              
        for (let i=0 ;i<length; i++){
            let minIndex =findMin(ary);  //找出第一小的值，宣告一個function return回來的值
            result.push(ary[minIndex])   //把第一小的值放入array
            ary.splice(minIndex,1)       //刪除第一小的值
        }
    return result
    }
console.log(sort([6, 8, 3, 2,]))
```
### 練習二：壓平陣列 (遞迴)
請寫出一個 function flatten，接收一個多維陣列並回傳「壓平」後的陣列。

flatten([1, 2, 3]) 預期回傳值：[1, 2, 3]

flatten([1, 2, [1, 2], [1, 3], 6]) 預期回傳值：[1, 2, 1, 2, 1, 3, 6]

flatten([1, [2, [3, [4]], 5], 6]) 預期回傳值：[1, 2, 3, 4, 5, 6]

```js
function flatten (ary){
    let result =[];                         //記錄點
    for (let i = 0;i<ary.length;i++){
    if (Array.isArray(ary[i])){             //發現陣列中有Array，
        let flat = flatten(ary[i])          // [1,2,3] 一直呼叫自己，呼叫壓平的function
        flat.forEach(function(value){       //把array 鐘的數傳進result
            result.push(value)
        })
    }else {
        result.push(ary[i])
    }
}
    return result
}

console.log(flatten([1, 2, [1, 2], [1, 3], 6]))
console.log(flatten([1, [2, [3, [4]], 5], 6]))

```
### 練習三：印出聖誕樹

```js
請寫一個 function tree，接收一個數字 n，按照規律列印出大小為 n 的聖誕樹

（這邊編輯器有點問題空白顯示不出來，用 _ 代表空白）
tree(1) 預期輸出：
*

tree(2) 預期輸出：

_*
***
_*
_*
tree(5) 預期輸出：.

____*
___***
__*****
_*******
*********
____*
____*
____*
____*
____*
```

```js
function printTopTree(n) {
  for (let i = 1; i <= n; i += 1) {
    const top = ' '.repeat(n - i) + '*'.repeat(2*i - 1);
    console.log(top);
  }
}

function printBottomTree(n) {
  for (let i = 1; i <= n; i += 1) {
    const bottom = ' '.repeat(n) + '*'.repeat(1);
    console.log(bottom);
  }
}


function tree(n) {
  printTopTree(n);
  printBottomTree(n);
}

tree(10);
```
### 練習四：判斷圈圈叉叉勝負
請寫出一個 function winner，接收一個代表圈圈叉叉的陣列，並回傳贏的是 O 還是 X，如果平手或還沒下完，請回傳 draw。

winner([
['O', 'O', 'X'],
['O', 'X', 'X'],
['O', 'X', 'O']
]) 預期回傳值：O

winner([
['O', 'O', 'X'],
['O', 'X', 'X'],
['X', 'X', 'O']
]) 預期回傳值：X

winner([
['O', 'O', 'X'],
['O', 'O', 'X'],
['X', 'X', '']
]) 預期回傳值：draw

```js
function winner(ary){
    for (let i = 0; i <3 ;i++)
        if(ary[0][i]===ary[1][i] && ary[1][i]===ary[2][i]){
            return ary[0][i]
        }else if(ary[i][0]===ary[i][1] && ary[i][1]===ary[i][2]){
            return ary[i][0]}
        else if(ary[0][0]===ary[1][1] && ary[1][1]===ary[2][2]){
                return ary[0][0]}
                else if(ary[0][2]===ary[1][1] && ary[1][1]===ary[2][0]){
                    return ary[0][2]}
                    return 'draw'
    
}
console.log(winner([
    ['O', 'O', 'X'],
    ['O', 'O', 'X'],
    ['X', 'X', '']
    ]))
```
### 練習五：判斷質數
請寫出一個 function isPrime，給定一個數字 n，回傳 n 是否為質數。
（質數的定義：除了 1 以外，沒辦法被所有 < n 的正整數整除）

isPrime(1) 正確回傳值：false

isPrime(5) 正確回傳值：true

isPrime(37) 正確回傳值：true
```js
function isPrime(n){
    if (n ===1) return false  
    for (let i = 2 ;i<=n-1;i++)  
    if(n%i ===0){
            return false
        }return true

}
for (var i =1 ; i<30;i++){
    console.log(i+':'+isPrime(i))
}

```
