### hw1：好多星星
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
### hw2：大小寫互換

```js
function alphaSwap(n){
    let result = '';
        for (let i = 0; i <n.length; i+=1){
            if('a'<=n[i] && n[i]<='z' ){
                result += n[i].toUpperCase()
            }else if ('A'<=n[i] && n[i]<='Z' ){
                result += n[i].toLowerCase()
            }else result += n[i]
        }
        
        
        return result
}


console.log(alphaSwap("abcd")) 
        
        return result
}
```
### hw3：判斷質數 

```js
function isPrime (n){
        if (n===1)return false
        for (let i = 2; i<n; i++){
            if(n % i === 0){
                return false
            }
        }return true
}
```
### hw4：判斷迴文

```js
function isPalindromes (str){
    
    let len = str.length
        for (let i = 0; i < len; i+=1){
            if(str === reverse(str)){                
                return true
            }return false
}
}

function reverse(str){
    let sum = '';                           
    for (var i =str.length ;i >=0 ;i-=1){     
    sum += str.charAt(i)                      
}
return sum                                  
}
```

### 大數加法

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
```
