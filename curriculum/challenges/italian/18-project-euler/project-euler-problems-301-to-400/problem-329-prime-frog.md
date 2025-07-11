---
id: 5900f4b51000cf542c50ffc8
title: 'Problema 329: rana prima'
challengeType: 1
forumTopicId: 301986
dashedName: problem-329-prime-frog
---

# --description--

Susan ha una rana prima.

La sua rana sta saltando su 500 quadrati numerati da 1 a 500.

Può saltare soltanto di un quadrato a sinistra o a destra, con la stessa probabilità, e non può saltare fuori dall'intervallo [1,500]. (se atterra alle estremità, salta automaticamente sull'unico quadrato disponibile nella mossa successiva.)

Quando è su un quadrato con un numero primo su di esso, gracida 'P' (PRIMO) con probabilità $\frac{2}{3}$ o 'N' (NON PRIMO) con probabilità $\frac{1}{3}$ poco prima di saltare sul quadrato successivo. Quando è su un quadrato con un numero su di esso che non è un primo gracida 'P' con probabilità $\frac{1}{3}$ o 'N' con probabilità $\frac{2}{3}$ poco prima di saltare sul quadrato successivo.

Dato che la posizione di partenza della rana è casuale con la stessa probabilità per ogni quadrato, e dato che sente i suoi primi 15 gracidii, qual è la probabilità di sentire la sequenza PPPPNPPPNPN?

Dai la tua risposta sotto forma di stringa come una frazione `p/q` in forma semplificata.

# --hints--

`primeFrog()` dovrebbe restituire una stringa.

```js
asset.isString(primeFrog());
```

`primeFrog()` dovrebbe restiturie la stringa `199740353/29386561536000`.

```js
assert.strictEqual(primeFrog(), '199740353/29386561536000');
```

# --seed--

## --seed-contents--

```js
function primeFrog() {

  return true;
}

primeFrog();
```

# --solutions--

```js
// solution required
```
