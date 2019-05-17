[electric](#electric)

[sandkingdom](#sandkingdom)


[life_number](#life_number)


## blackgirl(75/100)
輸入說明
輸入會是一個長度小於等於 100 的陣列，裡面每一筆資料為一個字串，字串的格式為：

名字1<空格>名字2<空格>關係值

名字只會是英文字母而且不會超過10個字元，關係值是一個整數，如果關係值是正的，表示這兩個美眉是好朋友，如果關係值是負的，表示這兩個美眉之間處的不好，關係值得絕對值不會超過100。

輸出說明
請回傳一行兩個關係最不好的美眉的名字，用空格隔開，如果有兩組美眉關係一樣不好，回傳比較早出現在測試資料中的那組，如果所有的美眉關係沒有不好，請回傳字串「Are you kidding me?」

實作說明
請實作一個叫做pa的 function，接收一個陣列並回傳題目要求的輸出。

範例
pa(['TACO hanon 0', 'peggy Penny 74', 'Debbie MeiMei -66']) => Debbie MeiMei

題目出處
NPSC 2007 年國中組初賽

```js
function pa(obj) {
  const ary = [];
  let num = [];
  let origin = [];
  obj.forEach((e) => { ary.push(e.split(' ').map(Number)); });
  obj.forEach((e) => { origin.push(e.split(' ')); });
  ary.forEach((e) => { num.push(e[2]); });

  let min = Math.min.apply(null, num);

  for (let i = 0; i < origin.length; i += 1) {
    if (min >= 0) {
      return ('「Are you kidding me?」');
    } if (origin[i][2] == min) {
      return (`${origin[i][0]} ${origin[i][1]}`);
    }
  }
}


console.log(pa(['TACO hanon 0', 'peggy Penny 0', 'Debbie MeiMei 0', 'TACO hanon 0', 'peggy Penny 0']));

```
## 不公平的人，是誰？(100/100)

輸入說明
輸入會是兩個字串 M 與 N。其中M代表大郭的水槍射程，N代表小郭的水槍射程，注意為求精確，所有射程的長度單位均為奈米。

因為大郭弄來的水槍是22世紀的產物，故水槍的射程非常非常遠，最長可以到達400位數的數字（射程必為一非負整數）。

輸出說明
對每一組測試資料，你應該回傳一個字串，該列從小郭的角度出發（小郭雖然比較笨，但還是很奸詐的！），判斷這是不是一場公平的比賽（對於小郭來說，只要大郭的射程不比小郭大，就是一場公平的遊戲）。

若是對小郭有利的遊戲，則回傳「Fair」，若不是，則回傳「Unfair」

實作說明
請實作一個叫做pb的 function，接收兩個字串並回傳題目要求的輸出。

```js
function pb(M, N) {
  const big = M;
  const little = N;
  if (big.length < little.length) {
    return ('Fair');
  } if (big.length > little.length) {
    return ('Unfair');
  } if (big.length = little.length) {
    for (let i = 0; i < big.length; i += 1) {
      if (big[i] < little[i]) {
        return ('Fair');
      } if (big[i] > little[i]) {
        return ('Unfair');
      } if (big[i] = little[i]) {
        // empty
      }
    }
  }
}
//Unexpected assignment within an 'if' statement.

```
## 打不倒的空氣人 (100/100)
這篇文章包含兩個部份，前半段是n個由小寫字母組成的英文單字，後半段是一個數列A1, A2, …, Am 。將所有單字接成一個很長的字串，這個字串的第A1, A2, …, Am個字母拼成的單字就是網站的密碼。

例如文章前半為 the quick brown fox jumps over the lazy dog

數列是 30, 6, 10, 19, 30, 13

答案就是字串"thequickbrownfoxjumpsoverthelazydog"的第30, 6, 10, 19, 30, 13個字母"airman"

(註：字串index由1開始)

由於文章非常長，neko希望你能幫他寫一個簡單的程式算出他要的密碼。

輸入說明
輸入會是兩個陣列，第一個陣列包含各種英文單字，第二個陣列包含文中所提的數列，可以假設數字不會超過字串總長度。

輸出說明
請回傳解出的密碼

實作說明
請實作一個叫做pc的 function，接收兩個字串並回傳題目要求的輸出。

範例
pc(['ab', 'cd', 'ef'], [1, 4]) => ad

題目出處
NPSC 2007 年國中組初賽

```js
function pc(M, N) {
  const str = M.join('');
  let pwd = '';


  for (let i = 0; i < N.length; i += 1) {
    const index = N[i];
    pwd += str[index - 1];
  }
  return pwd;
}
```
## 白飯 (100/100)
輸入說明
輸入會是一個陣列，包含著 n 個整數(0 < n <= 1000)，每個整數 Ai(0 <= Ai <= 100)代表第 i 個學生的分數。

輸出說明
請回傳低於平均的學生人數。

實作說明
請實作一個叫做pd的 function，接收一個陣列並回傳題目要求的輸出。

範例
pd([1, 3, 5]) => 1

題目出處
NPSC 2007 年國中組初賽

```js
function pd(n) {
  const avg = n.reduce((acc, cur) => acc + cur) / n.length;
  const result = n.filter(item => item < avg);
  return result.length;
}
```
## 友好數 (0/0)
輸入說明
輸入會是一個介於 2 與1000000 之間的數字 n。

輸出說明
對輸入的每個數 n，請試著找出是否存在某個數 m，使得 n 和 m 是友好數。如果有，請回傳 m，如果 n 和它自己形成友好數（也就是 n 的真因數和剛好也是 n）則回傳 =n，否則回傳 0。

注意：這邊的回傳值請統一回傳字串型態。

實作說明
請實作一個叫做pe的 function，接收一個數字並回傳題目要求的輸出。

範例
pe(6) => =6
pe(7) => 0
pe(220) => 284

題目出處
NPSC 2007 年國中組決賽

```js
function factor(m, n) {
  let sumM = 0;
  let sumN = 0;

  for (let i = 1; i < m; i += 1) {
    if (m % i === 0) {
      sumM += i;
    }
  }
  for (let i = 1; i < n; i += 1) {
    if (n % i === 0) {
      sumN += i;
    }
  }

  if (sumM === n && sumN === m) {
    return n;
  } if (sumM !== n ) {
    return 0;
  }
}

console.log(factor(6 ,6));

```
## 優惠方案 (100/100)
輸入說明
輸入會是一個字串，其中包含了三個整數，分別為顧客購買商品的價格，格式如下：

價格 1<空格>價格 2<空格>價格 3

其中價格都不會超過 10000。

輸出說明
對每組測試資料，判定三個價格是否皆不相等，若是則回傳 YES，若不 是則回傳 NO。

實作說明
請實作一個叫做pa的 function，接收一個字串並回傳題目要求的輸出。

範例
pa('10 10 10') => NO
pa('10 10 20') => NO
pa('20 10 10') => NO
pa('10 30 20') => YES

題目出處
NPSC 2008 年國中組初賽

```js
function pa(n) {
  const num = n.match(/\d+/g).map(Number);

  if (num[0] === num[1] || num[1] === num[2] || num[0] === num[2]) {
    return 'NO';
  } if (num[0] !== num[1] && num[1] !== num[2] && num[0] !== num[2]) {
    return 'YES';
  }
}

console.log(pa('80 90 90'));
```
## 首領的名字 (0/0)

輸入說明
輸入會是一個字串 S 跟一個陣列 M。

S 是一個汙漬的名字，名字皆為小寫英文字母，而汙漬用#號表示，請注意#代表任意長度和任意字母的汙漬。 M 的每一個元素為測試的名字，名字也都是小寫字母。

名字的長度不會超過 100。

輸出說明
對每組測試資料，請回傳一個跟陣列 M 長度相同的陣列，其中每一個元素為第 i 個名字可不可能為首領的名字，可能則輸出 POSSIBLE，不可能則輸出 IMPOSSIBLE。

實作說明
請實作一個叫做pb的 function，接收輸入回傳題目要求的輸出。

範例
pb('jam#s', ['john', 'james', 'jam', 'jambus']) => ['IMPOSSIBLE', 'POSSIBLE', 'IMPOSSIBLE', 'POSSIBLE']
pb('sa#', ['sally', 'sa', 'susan']) => ['POSSIBLE', 'POSSIBLE', 'IMPOSSIBLE']

題目出處
NPSC 2008 年國中組初賽


```js
function pb(S, M) {
  const len = S.length;
  const re = /[#]/g;
  const index = S.search(re);
  const result = [];
  console.log(index);
  for (let i = 0; i < M.length; i += 1) {
    if (S.slice(0, index) !== M[i].slice(0, index)) {
        result.push('IMPOSSIBLE');
      }
    if (index !== (len - 1) && M[i].length < len) {
      result.push('IMPOSSIBLE');
    }  
  }result.push('POSSIBLE');
  console.log(result);
}

console.log(pb('sa#', ['sally', 'safd', 'susan']));
```
## electric

請你根據下 面這個規則，設計一套電費計算系統。

(1) 電梯上樓時，每經過一個樓層，要花電費 20 元。
(2) 電梯下樓時，每經過一個樓層，要花電費 10 元。
(3) 你可以假設電梯停在某一個樓層時不會耗電。

舉例來說：今天有一個電梯從 2 樓到 8 樓再到 5 樓，則所耗的電費為：從 2 樓到 8 樓，所耗的電費是(8-2) x 20 = 120 元。電梯從 8 樓到 5 樓，所耗的電費是 (8-5) x 10 = 30 元。所以總共花了 150 元。

輸入說明
輸入會是一個字串 S，是一組以空白分隔的數字，分別表示電梯先後停過的樓層。電梯樓層最高不會超過 101 樓。

輸出說明
請根據電梯上下運作的樓層，計算出在一日中電梯運作所花的電費。（為了節能減碳，每日電費最高不會超過 10,000 元。）

實作說明
請實作一個叫做pc的 function，接收輸入回傳題目要求的輸出。

範例
pc('2 8 5') => 150
pc('2 9 7 3 4 6 1') => 310

題目出處
NPSC 2008 年國中組初賽

```js
function pc(S) {
  const num = S.split(' ').map(Number);
  let money = 0;

  for (let i = 0; i < num.length; i += 1) {
    if (num[i] < num[i + 1]) {
      money += (num[i + 1] - num[i]) * 20;
    } if (num[i] > num[i + 1]) {
      money += (num[i] - num[i + 1]) * 10;
    } if (num[i] = num[i + 1]) {
    }
  }

  return money;
}

console.log(pc('2 8 8 5 5'));
```
## sandKingdom
從前有個叫做「阿拉巴斯坦」的沙漠王國，住著一群和沙漠對抗、樂天知命的人。在沙漠生存，水源是非常稀有和珍貴的，即使是一滴也不能浪費。為了讓人民能夠節約和好好地衡量自己的取水量，在這個國家所有的水井旁邊都放了 1 公升、3 公升、9 公升、27 公升的四種公用水桶，可以讓人民自行取用。然而在水井打水有個奇特的規定：一定要把公用水桶裝滿才能帶走。

例如，住在猷巴村愛喝水的魯夫大叔家裡有個 25 公升的大木桶，每天他都會把這 25 公升的大木桶裝滿並且喝個精光。為了恰好裝滿 25 公升的大水桶而不浪費，每天早上，他先用 3 公升的水桶打 7 趟水、再用 1 公升的水桶打 4 趟水，來來回回跑個 11 趟，就可以恰好裝滿他家的大水桶而不浪費。

聰明的你應該已經發現，其實他也可以用 9 公升的水桶打 2 趟水，再用 3 公升的水桶打 2 趟水、最後再用 1 公升的水桶打 1 趟水，這樣他就只需要跑 5 趟到井邊裝水。

為了讓魯夫大叔能夠節省打水的時間，給定任何大水桶的容量 P (公升)，你能不能幫魯夫大叔找出裝滿他家的大水桶所需要的最少的裝水次數呢？

輸入說明
輸入會是一個數字 P 表示魯夫大叔家裡大水桶的容量(公升)， 1 <= P <= 500

輸出說明
對每組測試資料，請回傳魯夫大叔最少需要打幾趟水。

實作說明
請實作一個叫做pd的 function，接收輸入並回傳題目要求的輸出。

範例
pd(1) => 1
pd(29) => 3
pd(100) => 6

題目出處
NPSC 2008 年國中組初賽

```js
function pd(n) {
    let sum;
const a = parseInt(n/27,10);
const b = parseInt((n%27)/9,10);
const c = parseInt((n%27%9)/3,10);
const d = parseInt((n%27%9%3)/1,10);
 sum = a + b +c +d;
return sum
}

console.log(pd(100));
```
## life_number
生命靈數的算法是這樣的，給你某人的出生年月日，把每一位數字拆開後相加，如果總和不是個位數，就繼續把每一位數字拆開後相加，反覆做到結果是個位數為止，最後得到的個位數字就是生命靈數。

例如：1995 年 5 月 27 日
1+9+9+5+5+2+7 = 38
3+8 = 11
1+1 = 2
輸入說明
輸入會是一個描述出生年月日的字串，格式為 yyyymmdd。

例如說 1995 年 5 月 27 日會被表示為：19950527

輸出說明
針對每個女生的生日，輸出生命靈數 L，以及 L 是否為 2。

L 等於 2 的時候請輸出 Yes，其他的情況則輸出 No。

例如說 1995 年 5 月 27 日的輸出是：2, Yes

實作說明
請實作一個叫做pa的 function，接收輸入並回傳題目要求的輸出。

範例
pa('19950527') => 2, Yes
pa('19971205') => 7, No
pa('19960913') => 2, Yes

題目出處
NPSC 2009 年國中組初賽
```js
function pa(sum) {
  const a = sum.split('').map(Number).reduce((acc, cur) => acc + cur);
  const b = a.toString().split('').map(Number).reduce((acc, cur) => acc + cur);
  const c = b.toString().split('').map(Number).reduce((acc, cur) => acc + cur);

  if (c === 2) {
    return `${c}, Yes`;
  } if (c !== 2) {
    return `${c}, No`;
  }
}
console.log(pa('19950527'));

```
