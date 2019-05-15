## hw1：好多星星  
給定 n（1<=n<=30），依照規律「回傳」正確圖形（每一行是一個陣列的元素）

```
n = 1
["*"]

n = 3
["*", "**", "***"]

n = 6
["*", "**", "***", "****", "*****", "******"]
```
```js
function stars(n) {
  const result = [];
  for (let i = 1; i <= n; i += 1) {
    result.push('*'.repeat(i));
  }

  return result;
}

console.log(stars(6));

```
## hw2：大小寫互換
給定一字串，把小寫字母轉成大寫，大寫字母轉成小寫之後回傳，若不是英文字母則忽略。

```
input: nick
output: NICK

input: Nick
output: nICK

input: ,hEllO122
output: ,HeLLo123
```

```js
function alphaSwap(n) {
  let result = '';
  for (let i = 0; i < n.length; i += 1) {
    if (n[i] >= 'a' && n[i] <= 'z') {
      result += n[i].toUpperCase();
    } else if (n[i] >= 'A' && n[i] <= 'Z') {
      result += n[i].toLowerCase();
    } else result += n[i];
  }
  return result;
}

console.log(alphaSwap('abDd'));

```
## hw3：判斷質數
給定一個數字 n（1<=n<=100000），請回傳 n 是否為質數（質數的定義：除了 1 以外，所有小於他的數都無法整除）

```
n = 2 => true
n = 3 => true
n = 10 => false
n = 37 => true
n = 38 => false
```

```js
function isPrime(n) {
  if (n === 1) return false;
  for (let i = 2; i < n; i += 1) {
    if (n % i === 0) {
      return false;
    }
  } return true;
}

console.log(isPrime(7))

```
## hw4：判斷迴文
給定一個長度小於 100 的字串 s，請回傳 s 是否為迴文（迴文的定義：正著唸倒著念都一樣）

```
abcba => true
apple => false
aaaaa => true
applppa => true
```


```js
function reverse(str) {
  let sum = '';
  for (let i = str.length; i >= 0; i -= 1) {
    sum += str.charAt(i);
  }
  return sum;
}

function isPalindromes(str) {
  const len = str.length;
  for (let i = 0; i < len; i += 1) {
    if (str === reverse(str)) {
      return true;
    }
  } return false;
}

console.log(isPalindromes('aaaaabcbbaaaaa'));
```

## hw5：大數加法
給定兩個長度為 l(1<=l<=1000)的數字（但型態為字串），請回傳兩個數字相加後的結果。  

提示：

1. 這題不是要考你型態轉換，而且這題很難，真的很難
2. 小時候怎麼做直式加法，這一題就怎麼做，可以拿紙跟筆試試看

```
"123"+"456" => "579"
"12312383813881381381"+"129018313819319831" => "12441402127700701212"
```

```js
function add(a, b) {
  const result = [];
  let numA = '';
  let numB = '';

  if (a.length > b.length) {
    numB = '0'.repeat(a.length - b.length) + b;
    numA = a;
  } else {
    numA = '0'.repeat(b.length - a.length) + a;
    numB = b;
  }
  const aryA = numA.split('');
  const aryB = numB.split('');

  for (let i = 0; i < numA.length; i += 1) {
    result.push(parseInt(aryA[i], 10) + parseInt(aryB[i], 10));
  }
  const newArray = [];
  for (let i = numA.length - 1; i >= 0; i -= 1) {
    if (result[i] >= 10) {
      newArray.unshift(result[i] - 10);
      result[i - 1] += 1;
    } else {
      newArray.unshift(result[i]);
    }
  }
  return (newArray.join(''));
}

console.log(add('12312383813881381381', '129018313819319831'));
```
