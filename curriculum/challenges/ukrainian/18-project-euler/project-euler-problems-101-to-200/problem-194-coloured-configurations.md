---
id: 5900f42f1000cf542c50ff40
title: 'Problem 194: Colored Configurations'
challengeType: 1
forumTopicId: 301832
dashedName: problem-194-coloured-configurations
---

# --description--

Розглянемо графи з елементами A: <img alt="graph unit A" src="https://cdn.freecodecamp.org/curriculum/project-euler/coloured-configurations-1.png" style="display: inline-block; background-color: white; padding: 10px;" /> та B: <img  alt="graph unit B" src="https://cdn.freecodecamp.org/curriculum/project-euler/coloured-configurations-2.png" style="display: inline-block; background-color: white; padding: 10px;" />, де елементи з’єднані між собою по вертикальних сторонах, як на графі <img alt="graph with four units glued along the vertical edges" src="https://cdn.freecodecamp.org/curriculum/project-euler/coloured-configurations-3.png" style="display: inline-block; background-color: white; padding: 10px;" />.

A configuration of type $(a,b,c)$ is a graph thus built of $a$ units A and $b$ units B, where the graph's vertices are colored using up to $c$ colors, so that no two adjacent vertices have the same color. Складений граф вище є прикладом виду $(2,2,6)$, а точніше $(2,2,c)$ за умови $c ≥ 4$

Нехай $N(a,b,c)$ є кількістю конфігурацій виду $(a,b,c)$. Наприклад, $N(1,0,3) = 24$, $N(0,2,4) = 92928$ та $N(2,2,3) = 20736$.

Знайдіть останні 8 цифр в $N(25,75,1984)$.

# --hints--

`coloredConfigurations()` має повернути `61190912`.

```js
assert.strictEqual(coloredConfigurations(), 61190912);
```

# --seed--

## --seed-contents--

```js
function coloredConfigurations() {

  return true;
}

coloredConfigurations();
```

# --solutions--

```js
// solution required
```
