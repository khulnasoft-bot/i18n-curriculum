---
id: 5900f4801000cf542c50ff92
title: 'Problema 275: sculture bilanciate'
challengeType: 1
forumTopicId: 301925
dashedName: problem-275-balanced-sculptures
---

# --description--

Definiamo una scultura bilanciata di ordine $n$ come segue:

- Un polimino fatto di $n + 1$ mattonelle noti come i blocchi ($n$ mattonelle) e il plinto (la mattonella rimanente);
- the plinth has its center at position ($x = 0$, $y = 0$);
- i blocchi hanno coordinate $y$ maggiori di zero (quindi il plinto è l'unica piastrella più in basso);
- the center of mass of all the blocks, combined, has $x$-coordinate equal to zero.

Quando si contano le strutture, qualsiasi arrangiamento che è una semplice riflessione lungo l'asse $y$, <u>non</u> viene contato come distinto. Per esempio, le 18 sculture bilanciate di ordine 6 sono mostrate di seguito; nota che ogni coppia d'immagini specchiate (intorno all'asse $y$) è contata come una sola scultura:

<img alt="18 sculture bilanciate di ordine 6" src="https://cdn.freecodecamp.org/curriculum/project-euler/balanced-sculptures.gif" style="background-color: white; padding: 10px; display: block; margin-right: auto; margin-left: auto; margin-bottom: 1.2rem;" />

Ci sono 964 sculture bilanciate di ordine 10 e 360505 di ordine 15.

Quante sculture bilanciate di ordine 18 ci sono?

# --hints--

`balancedSculptures()` dovrebbe restituire `15030564`.

```js
assert.strictEqual(balancedSculptures(), 15030564);
```

# --seed--

## --seed-contents--

```js
function balancedSculptures() {

  return true;
}

balancedSculptures();
```

# --solutions--

```js
// solution required
```
