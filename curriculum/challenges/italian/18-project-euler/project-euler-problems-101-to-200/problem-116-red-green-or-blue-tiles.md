---
id: 5900f3e01000cf542c50fef3
title: 'Problema 116: piastrelle rosse, verdi o blu'
challengeType: 1
forumTopicId: 301742
dashedName: problem-116-red-green-or-blue-tiles
---

# --description--

A row of five black square tiles is to have a number of its tiles replaced with colored oblong tiles chosen from red (length two), green (length three), or blue (length four).

Se si scelgono piastrelle rosse ci sono esattamente sette modi per farlo.

<img alt="Possibili modi di posizionare piastrelle oblunghe rosse su una fila con lunghezza di cinque unità" src="https://cdn.freecodecamp.org/curriculum/project-euler/red-green-or-blue-tiles-1.png" style="background-color: white; padding: 10px; display: block; margin-right: auto; margin-left: auto; margin-bottom: 1.2rem;" />

Se si scelgono piastrelle verdi ci sono tre modi.

<img alt="Possibili modi di posizionare piastrelle oblunghe verdi su una fila con lunghezza di cinque unità" src="https://cdn.freecodecamp.org/curriculum/project-euler/red-green-or-blue-tiles-2.png" style="background-color: white; padding: 10px; display: block; margin-right: auto; margin-left: auto; margin-bottom: 1.2rem;" />

E se si scelgono piastrelle blu ci sono due modi.

<img alt="Possibili modi di posizionare piastrelle oblunghe blu su una fila con lunghezza di cinque unità" src="https://cdn.freecodecamp.org/curriculum/project-euler/red-green-or-blue-tiles-3.png" style="background-color: white; padding: 10px; display: block; margin-right: auto; margin-left: auto; margin-bottom: 1.2rem;" />

Supponendo che i colori non possano essere mescolati ci sono 7 + 3 + 2 = 12 modi per sostituire le piastrelle nere in una riga che misura cinque unità di lunghezza. In quanti modi diversi si possono sostituire le piastrelle nere in una fila di cinquanta unità di lunghezza se i colori non possono essere mescolati e si deve usare almeno una piastrella colorata?

**Nota:** questo problema è correlato al problema 117.

# --hints--

`redGreenBlueOne()` dovrebbe restituire `20492570929`.

```js
assert.strictEqual(redGreenBlueOne(), 20492570929);
```

# --seed--

## --seed-contents--

```js
function redGreenBlueOne() {

  return true;
}

redGreenBlueOne();
```

# --solutions--

```js
// solution required
```
