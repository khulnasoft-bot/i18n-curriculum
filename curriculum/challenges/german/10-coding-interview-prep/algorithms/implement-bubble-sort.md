---
id: 8d5123c8c441eddfaeb5bdef
title: Implementiere einen Bubblesort-Algorithmus
challengeType: 1
forumTopicId: 301612
dashedName: implement-bubble-sort
---

# --description--

This is the first of several challenges on sorting algorithms. Given an array of unsorted items, we want to be able to return a sorted array. We will see several different methods to do this and learn some tradeoffs between these different approaches. While most modern languages have built-in sorting methods for operations like this, it is still important to understand some of the common basic approaches and learn how they can be implemented.

Hier werden wir einen Bubblesort-Algorithmus verwenden. Die Bubblesort-Methode beginnt am Anfang eines unsortierten Arrays und "bläst" unsortierte Werte zum Ende hin auf, wobei sie das Array so lange durchläuft, bis es vollständig sortiert ist. Dazu vergleicht es benachbarte Elemente und tauscht sie aus, wenn sie nicht in der richtigen Reihenfolge sind. Die Methode läuft so lange in einer Schleife durch das Array, bis keine Änderungen mehr vorgenommen werden und das Array schlussendlich sortiert ist.

Diese Methode erfordert mehrere Iterationen durch das Array und hat im Durchschnitt oder im schlimmsten Fall eine quadratische Zeitkomplexität. Obwohl die Methode einfach ist, ist sie meistens sehr unpraktisch.

**Anleitung:** Schreibe eine Funktion `bubbleSort`, die ein Array mit ganzen Zahlen als Eingabe verwendet und ein Array mit diesen ganzen Zahlen in sortierter Reihenfolge vom kleinsten zum größten Wert zurückgibt.

# --hints--

`bubbleSort` sollte eine Funktion sein.

```js
assert.isFunction(bubbleSort);
```

`bubbleSort` sollte ein sortiertes Array zurückgeben (vom kleinsten zum größten).

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

`bubbleSort([1,4,2,8,345,123,43,32,5643,63,123,43,2,55,1,234,92])` soll ein, bis auf die Reihenfolge, unverändertes Array zurückgeben.

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

`bubbleSort` soll nicht die eingebaute Methode `.sort()` verwenden.

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
