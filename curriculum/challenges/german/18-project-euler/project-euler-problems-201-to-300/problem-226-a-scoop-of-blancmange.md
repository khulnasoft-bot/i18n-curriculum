---
id: 5900f4511000cf542c50ff62
title: 'Problem 226: Eine Kugel Blancmange'
challengeType: 1
forumTopicId: 301869
dashedName: problem-226-a-scoop-of-blancmange
---

# --description--

Die Takagi-Funktion (Blancmange) ist ein Satz von Punkten ($x$,$y$), so dass $0 ≤ x ≤ 1$ und $\displaystyle y = \sum_{n = 0}^{\infty} \frac{s(2^nx)}{2^n}$, $s(x)$ die Entfernung von $x$ zum nächsten Integer ist.

Der Bereich unter der Takagi-Funktion ist gleich $\frac{1}{2}$, im folgenden Diagram in rosa dargestellt.

<img alt="diagramm der Takagi-Funktion, wobei der Kreis C im Diagramm dargestellt ist" src="https://cdn.freecodecamp.org/curriculum/project-euler/a-scoop-of-blancmange.gif" style="background-color: white; padding: 10px; display: block; margin-right: auto; margin-left: auto; margin-bottom: 1.2rem;" />

Let $C$ be the circle with center ($\frac{1}{4}$,$\frac{1}{2}$) and radius $\frac{1}{4}$, shown in black in the diagram.

Welcher Bereich unter der Takagi-Funktion ist von $C$ eingeschlossen? Gib deine Antwort gerundet auf acht Dezimalstellen in Form 0.abcdefgh an

# --hints--

`scoopOfBlancmange()` sollte `0.11316017` zurückgeben.

```js
assert.strictEqual(scoopOfBlancmange(), 0.11316017);
```

# --seed--

## --seed-contents--

```js
function scoopOfBlancmange() {

  return true;
}

scoopOfBlancmange();
```

# --solutions--

```js
// solution required
```
