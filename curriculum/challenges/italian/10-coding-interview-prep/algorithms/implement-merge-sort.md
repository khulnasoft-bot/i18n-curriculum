---
id: 587d825c367417b2b2512c8f
title: Implementare Merge Sort
challengeType: 1
forumTopicId: 301614
dashedName: implement-merge-sort
---

# --description--

Another common intermediate sorting algorithm is merge sort. Like quick sort, merge sort also uses a divide-and-conquer, recursive methodology to sort an array. It takes advantage of the fact that it is relatively easy to sort two arrays as long as each is sorted in the first place. But we'll start with only one array as input, so how do we get to two sorted arrays from that? Well, we can recursively divide the original input in two until we reach the base case of an array with one item. A single-item array is naturally sorted, so then we can start combining. This combination will unwind the recursive calls that split the original array, eventually producing a final sorted array of all the elements. The steps of merge sort, then, are:

**1)** Dividi ricorsivamente l'array di input a metà finché non viene prodotto un sotto-array con un solo elemento.

**2)** Unisci tutti i sottoarray ordinati per produrre l'array finale ordinato.

Il Merge Sort è un metodo di ordinamento efficiente, con complessità temporale di *O(nlog(n))*. Questo algoritmo è popolare perché è performante e relativamente facile da implementare.

A parte questo, questo sarà l'ultimo algoritmo di ordinamento che tratteremo qui. Tuttavia, più tardi nella sezione sulle strutture di dati ad albero descriveremo Heap Sort, un altro metodo di ordinamento efficiente che richiede un heap binario nella sua implementazione.

**Istruzioni:** Scrivi una funzione `mergeSort` che prende un array di interi come input e restituisce un array di questi interi in ordine dal più piccolo al più grande. Un buon modo per implementarlo è quello di scrivere una funzione, per esempio `merge`, che si occupa dell'unione di due array, e un'altra funzione, per esempio `mergeSort`, che è responsabile della ricorsione e che produce array di elementi singoli da fornire a Merge. Buona fortuna!

# --hints--

`mergeSort` dovrebbe essere una funzione.

```js
assert.isFunction(mergeSort);
```

`mergeSort` dovrebbe restituire un array ordinato (dal più piccolo al più grande).

```js
function isSorted(a){
  for(let i = 0; i < a.length - 1; i++)
    if(a[i] > a[i + 1])
      return false;
  return true;
}
assert.isTrue(
  isSorted(
    mergeSort([
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

`mergeSort([1,4,2,8,345,123,43,32,5643,63,123,43,2,55,1,234,92])` dovrebbe restituire un array invariato tranne che per l'ordine.

```js
assert.sameMembers(
  mergeSort([
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

`mergeSort` non dovrebbe utilizzare il metodo integrato `.sort()`.

```js
function isBuiltInSortUsed(){
  let sortUsed = false;
  const temp = Array.prototype.sort;
  Array.prototype.sort = () => sortUsed = true;
  try {
    mergeSort([0, 1]);
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
function mergeSort(array) {
  // Only change code below this line
  return array;
  // Only change code above this line
}
```

# --solutions--

```js
function mergeSort(array) {
  if (array.length === 1) {
    return array;
  } else {
    const splitIndex = Math.floor(array.length / 2);
    return merge(
      mergeSort(array.slice(0, splitIndex)),
      mergeSort(array.slice(splitIndex))
    );
  }

  // Merge two sorted arrays
  function merge(array1, array2) {
    let merged = [];
    while (array1.length && array2.length) {
      if (array1[0] < array2[0]) {
        merged.push(array1.shift());
      } else if (array1[0] > array2[0]) {
        merged.push(array2.shift());
      } else {
        merged.push(array1.shift(), array2.shift());
      }
    }

    // After looping ends, one array is empty, and other array contains only
    // values greater than all values in `merged`
    return [...merged, ...array1, ...array2];
  }
}

mergeSort([1, 4, 2, 8, 345, 123, 43, 32, 5643, 63, 123, 43, 2, 55, 1, 234, 92]);
```
