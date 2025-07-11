---
id: 5900f4931000cf542c50ffa6
title: 'Завдання 295: лінзоподібні отвори'
challengeType: 1
forumTopicId: 301947
dashedName: problem-295-lenticular-holes
---

# --description--

Опукла область, охоплена двома колами, називається лінзоподібним отвором, якщо:

- The centers of both circles are on lattice points.
- Два кола перетинаються в двох різних точках сітки.
- Внутрішня частина опуклої області, охопленої двома колами, не містить точок сітки.

Розглянемо ці кола:

$$\begin{align}   & C_0: x^2 + y^2 = 25 \\\\
  & C_1: {(x + 4)}^2 + {(y - 4)}^2 = 1 \\\\ & C_2: {(x - 12)}^2 + {(y - 4)}^2 = 65 \end{align}$$

Кола $C_0$, $C_1$ та $C_2$ намальовані на рисунку нижче.

<img alt="кола C_0, C_1 та C_2" src="https://cdn.freecodecamp.org/curriculum/project-euler/lenticular-holes.gif" style="background-color: white; padding: 10px; display: block; margin-right: auto; margin-left: auto; margin-bottom: 1.2rem;" />

Лінзоподібний отвір утворюють як $C_0$ та $C_1$, так і $C_0$ та $C_2$.

Впорядковану пару додатних дійсних чисел ($r_1$, $r_2$) називають лінзоподібною парою, якщо існують два кола з радіусами $r_1$ та $r_2$, які утворюють лінзоподібний отвір. Можна довести, що ($1$, $5$) та ($5$, $\sqrt{65}$) є лінзоподібними парами в прикладі вище.

Нехай $L(N)$ буде кількістю різних лінзоподібних пар ($r_1$, $r_2$), за яких $0 &lt; r_1 ≤ r_2 ≤ N$. Можна довести, що $L(10) = 30$ та $L(100) = 3442$.

Знайдіть $L(100\\,000)$.

# --hints--

`lenticularHoles()` має повернути `4884650818`.

```js
assert.strictEqual(lenticularHoles(), 4884650818);
```

# --seed--

## --seed-contents--

```js
function lenticularHoles() {

  return true;
}

lenticularHoles();
```

# --solutions--

```js
// solution required
```
