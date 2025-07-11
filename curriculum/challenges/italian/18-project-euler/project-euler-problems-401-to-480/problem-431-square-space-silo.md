---
id: 5900f51b1000cf542c51002e
title: 'Problema 431: silo spaziale quadrato'
challengeType: 1
forumTopicId: 302102
dashedName: problem-431-square-space-silo
---

# --description--

Fred il fattore fa installare un nuovo silo nella sua fattoria, e avendo un'ossessione per tutte le cose quadrate è assolutamente devastato quando scopre che è circolare. Quentin, il rappresentate dalla compagnia che installa il silo, spiega che li costruiscono solo tondi, ma fa notare che è appoggiato su una base quadrata. Fred non è divertito e insiste che sia rimosso dalla sua proprietà.

Pensando in fretta Quentin spiega che quando del materiale granulare è fatto cadere dall'alto si forma una curva conica e l'angolo naturale che si forma con l'orizzontale è chiamato angolo di riposo. For example if the angle of repose, $\alpha = 30°$, and grain is delivered at the center of the silo then a perfect cone will form towards the top of the cylinder. Nel caso del silo, che ha un diametro di 6m, l'ammontare di spazio sprecato è circa 32.648388556 m<sup>3</sup>. However, if grain is delivered at a point on the top which has a horizontal distance of $x$ metres from the center then a cone with a strangely curved and sloping base is formed. Mostra una immagine a Fred.

<img alt="immagine che presenta il formarsi del cono perfetto verso la cima del cilindro" src="https://cdn.freecodecamp.org/curriculum/project-euler/square-space-silo.png" style="background-color: white; padding: 10px; display: block; margin-right: auto; margin-left: auto; margin-bottom: 1.2rem;" />

L'ammontare dello spazio sprecato in metri cubi è dato da $V(x)$. Se $x = 1.114\\,785\\,284$, che ha tre al quadrato cifre decimali, allora l'ammontare di spazio sprecato, $V(1.114\\,785\\,284) \approx 36$. Dato il range di possibili soluzioni per questo problema c'è un'unica altra opzione: $V(2.511\\,167\\,869) \approx 49$. Sarebbe come sapere che il quadrato è il re del silo, in tutta la sua gloria sopra il tuo grano.

Gli occhi di Fred si illuminano di delizia a questa elegante risoluzione, ma ispezionando più attentamente il disegno e i calcoli di Quentin la sua felicità diventa sconforto ancora una volta. Fred fa notare a Quentin che è il raggio del silo che è 6 metri, non il diametro, e l'angolo di riposo del suo grano è 40°. Però, se Quentin può trovare un set di soluzioni per questo silo in particolare allora sarà felice di tenerlo.

Se Quentin deve soddisfare l'appetito di Fred per tutte le cose quadrate, allora determina i valori di $x$ per tutte le possibili situazioni di spazio sprecato quadrato, e calcola \sum x$ corretto con 9 cifre decimali.

# --hints--

`squareSpaceSilo()` dovrebbe restituire `23.386029052`.

```js
assert.strictEqual(squareSpaceSilo(), 23.386029052);
```

# --seed--

## --seed-contents--

```js
function squareSpaceSilo() {

  return true;
}

squareSpaceSilo();
```

# --solutions--

```js
// solution required
```
