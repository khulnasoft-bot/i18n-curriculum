---
id: 8d5123c8c441eddfaeb5bdef
title: Implementare Bubble Sort
challengeType: 1
forumTopicId: 301612
dashedName: implement-bubble-sort
---

# --description--

This is the first of several challenges on sorting algorithms. Given an array of unsorted items, we want to be able to return a sorted array. We will see several different methods to do this and learn some tradeoffs between these different approaches. While most modern languages have built-in sorting methods for operations like this, it is still important to understand some of the common basic approaches and learn how they can be implemented.

Qui vedremo il Bubble Sort. Il metodo di ordinamento Bubble Sort comincia all'inizio di un array non ordinato e 'porta a galla' i valori non ordinati verso la fine, iterando attraverso l'array fino a quando non è completamente ordinato. Lo fa confrontando gli elementi adiacenti e scambiandoli se sono fuori ordine. Il metodo continua a iterare attraverso l'array fino a quando non si verificano più scambi: a quel punto l'array è ordinato.

Questo metodo richiede iterazioni multiple attraverso l'array e per i casi medi e peggiori ha complessità di tempo quadratica. Per quanto semplice, è poco pratico nella maggior parte delle situazioni.

**Istruzioni:** Scrivi una funzione `bubbleSort` che prende un array di interi come input e restituisce un array di questi interi in ordine dal più piccolo al più grande.

# --hints--

`bubbleSort` dovrebbe essere una funzione.

```js
assert.isFunction(bubbleSort);
```

`bubbleSort` dovrebbe restituire un array ordinato (dal più piccolo al più grande).

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

`bubbleSort([1,4,2,8,345,123,43,32,5643,63,123,43,2,55,1,234,92])` dovrebbe restituire un array invariato tranne che per l'ordine.

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

`bubbleSort` non dovrebbe usare il metodo integrato `.sort()`.

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
