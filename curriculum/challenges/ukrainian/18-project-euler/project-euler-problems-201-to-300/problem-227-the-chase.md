---
id: 5900f44f1000cf542c50ff61
title: 'Завдання 227: погоня'
challengeType: 1
forumTopicId: 301870
dashedName: problem-227-the-chase
---

# --description--

«Погоня» — це гра з двома кубиками та парною кількістю гравців.

Гравці сидять за столом; гра починається з того, що два гравці навпроти один одного отримують по гральному кубику. За кожен хід два гравці кидають кубики.

If the player rolls a 1, he passes the die to his neighbor on the left.

If the player rolls a 6, he passes the die to his neighbor on the right.

За інших умов гравець тримає кубик до наступного ходу.

Гра закінчується, коли хтось із гравців отримує обидва кубики. Це означає, що той гравець програв.

Яка очікувана кількість ходів у грі зі 100 гравцями? Відповідь закругліть до десяти значущих цифр.

# --hints--

`theChase()` має повернути `3780.618622`.

```js
assert.strictEqual(theChase(), 3780.618622);
```

# --seed--

## --seed-contents--

```js
function theChase() {

  return true;
}

theChase();
```

# --solutions--

```js
// solution required
```
