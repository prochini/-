## 黑澀會美眉 (75/100)
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
