---
id: 5900f4b91000cf542c50ffcb
title: 'Завдання 332: сферичні трикутники'
challengeType: 1
forumTopicId: 301990
dashedName: problem-332-spherical-triangles
---

# --description--

Сферичний трикутник — це фігура, утворена на поверхні сфери трьома великими круговими дугами, що попарно перетинаються у трьох вершинах.

<img alt="сферичний трикутник, утворений на поверхні сфери" src="https://cdn.freecodecamp.org/curriculum/project-euler/spherical-triangles.jpg" style="background-color: white; padding: 10px; display: block; margin-right: auto; margin-left: auto; margin-bottom: 1.2rem;" />

Let $C(r)$ be the sphere with the center (0,0,0) and radius $r$.

Нехай $Z(r)$ буде набором точок з цілими координатами на поверхні $C(r)$.

Нехай $T(r)$ буде набором сферичних трикутників з вершинами в $Z(r)$. Вироджені сферичні трикутники, утворені трьома точками на одній великій дузі, <u>не</u> включені до $T(r)$.

Нехай $A(r)$ буде площею найменшого сферичного трикутника в $T(r)$.

Наприклад, $A(14)$ є 3.294040, округливши до шести знаків після коми.

Знайдіть $\displaystyle \sum_{r = 1}^{50} A(r)$. Дайте відповідь, заокруглену до шести знаків після коми.

# --hints--

`sphericalTriangles()` має повернути `2717.751525`.

```js
assert.strictEqual(sphericalTriangles(), 2717.751525);
```

# --seed--

## --seed-contents--

```js
function sphericalTriangles() {

  return true;
}

sphericalTriangles();
```

# --solutions--

```js
// solution required
```
