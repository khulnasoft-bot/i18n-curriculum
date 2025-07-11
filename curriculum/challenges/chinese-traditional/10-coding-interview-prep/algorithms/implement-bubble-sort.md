---
id: 8d5123c8c441eddfaeb5bdef
title: 實現冒泡排序
challengeType: 1
forumTopicId: 301612
dashedName: implement-bubble-sort
---

# --description--

This is the first of several challenges on sorting algorithms. Given an array of unsorted items, we want to be able to return a sorted array. We will see several different methods to do this and learn some tradeoffs between these different approaches. While most modern languages have built-in sorting methods for operations like this, it is still important to understand some of the common basic approaches and learn how they can be implemented.

在這裏我們將看到冒泡排序。 冒泡排序方法從未排序數組的開頭開始，並向末端“冒泡”未排序的值，遍歷數組直到它完全排序。 它是這樣實現的：比較相鄰的元素，如果它們的順序不對，就交換它們。 該方法繼續循環遍歷數組，直到沒有發生交換，此時數組已被排序。

這種方法需要對數組進行多次循環，對於平均和最壞的情況來說，其時間複雜性爲二次方。 雖然簡單，但在大多數情況下通常不切實際。

**說明：**寫一個 `bubbleSort` 函數，它將一個整數數組作爲輸入，並返回一個數組，其中的整數元素以從小到大的順序排列。

# --hints--

`bubbleSort` 應該是一個函數。

```js
assert.isFunction(bubbleSort);
```

`bubbleSort` 應該返回一個已排序的數組（從小到大）。

```js
function isSorted(a){
  for(let i = 0; i < a.length - 1; i++)
    if(a[i] > a[i + 1])
      return false;
  return true;
}
assert.isTrue(
  isSorted(
    bubbleSort([
      1,
      4,
      2,
      8,
      345,
      123,
      43,
      32,
      5643,
      63,
      123,
      43,
      2,
      55,
      1,
      234,
      92
    ])
  )
);
```

`bubbleSort([1,4,2,8,345,123,43,32,5643,63,123,43,2,55,1,234,92])` 應返回一個除順序外沒有變化的數組。

```js
assert.sameMembers(
  bubbleSort([
    1,
    4,
    2,
    8,
    345,
    123,
    43,
    32,
    5643,
    63,
    123,
    43,
    2,
    55,
    1,
    234,
    92
  ]),
  [1, 4, 2, 8, 345, 123, 43, 32, 5643, 63, 123, 43, 2, 55, 1, 234, 92]
);
```

`bubbleSort` 不應使用內置的 `.sort()` 方法。

```js
function isBuiltInSortUsed(){
  let sortUsed = false;
  const temp = Array.prototype.sort;
  Array.prototype.sort = () => sortUsed = true;
  try {
    bubbleSort([0, 1]);
  } finally {
    Array.prototype.sort = temp;
  }
  return sortUsed;
}
assert.isFalse(isBuiltInSortUsed());
```

# --seed--

## --seed-contents--

```js
function bubbleSort(array) {
  // Only change code below this line
  return array;
  // Only change code above this line
}
```

# --solutions--

```js
function bubbleSort(array) {
  for (let i = 0; i < array.length; i++) {
    let swapped = false;
    for (let j = 1; j < array.length; j++) {
      if (array[j - 1] > array[j]) {
        let temp = array[j-1];
        array[j-1] =  array[j];
        array[j] = temp;
        swapped = true;
      }
    }
    if (swapped === false) {
      break;
    }
  }
  return array;
}
```
