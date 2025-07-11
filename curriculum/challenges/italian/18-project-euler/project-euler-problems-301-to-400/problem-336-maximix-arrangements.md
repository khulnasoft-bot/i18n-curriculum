---
id: 5900f4bd1000cf542c50ffcf
title: 'Problema 336: arrangiamenti maximix'
challengeType: 1
forumTopicId: 301994
dashedName: problem-336-maximix-arrangements
---

# --description--

Un treno è utilizzato per trasportare quattro carrozze nell'ordine: $ABCD$. Tuttavia, a volte quando il treno arriva per raccogliere le carrozze, esse non sono nell'ordine corretto.

Per riorganizzare le carrozze, vengono tutte smistate su un grande disco rotante. Dopo che le carrozze sono disaccoppiate in un punto specifico, il treno si allontana dal disco rotante tirando le carrozze ancora attaccate a esso. Le carrozze rimanenti sono ruotate di 180°. Tutte le carrozze vengono poi ricongiunte e questo processo viene ripetuto tutte le volte necessarie a ottenere il minor numero di utilizzi del disco.

Alcune disposizioni, come $ADCB$, possono essere risolte facilmente: le carrozze sono separate tra $A$ e $D$, e dopo che $DCB$ sono stati ruotati l'ordine corretto è stato raggiunto.

Tuttavia, Simple Simon, il macchinista del treno, non è noto per la sua efficienza, così risolve sempre il problema ottenendo inizialmente il carrello $A$ nel posto corretto, poi la carrozza $B$, e così via.

Usando quattro carrozze, i peggiori arrangiamenti possibili per Simon, che chiamiamo maximix, sono $DACB$ e $DBAC$; ognuno richiede quattro rotazioni (anche se usando l'approccio più efficiente potrebbero essere risolti usando solo tre rotazioni). Il processo che usa per $DACB$ è mostrato sotto.

<img alt="cinque rotazioni per arrangiamento maximix DACB" src="https://cdn.freecodecamp.org/curriculum/project-euler/maximix-arrangements.gif" style="background-color: white; padding: 10px; display: block; margin-right: auto; margin-left: auto; margin-bottom: 1.2rem;" />

Possiamo verificare che ci sono 24 arrangiamenti maximix per sei carrozze, di cui il decimo arrangiamento lessicografico maximix è $DFAECB$.

Trova il ${2011}$-simo arrangiamento maximix lessicografico per undici carrozze.

# --hints--

`maximixArrangements()` dovrebbe restituire una stringa.

```js
asset.isString(maximixArrangements());
```

`maximixArrangements()` dovrebbe restituire la stringa `CAGBIHEFJDK`.

```js
assert.strictEqual(maximixArrangements(), 'CAGBIHEFJDK');
```

# --seed--

## --seed-contents--

```js
function maximixArrangements() {

  return true;
}

maximixArrangements();
```

# --solutions--

```js
// solution required
```
