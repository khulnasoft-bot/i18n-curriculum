---
id: 5900f3e51000cf542c50fef8
title: 'Завдання 121: призовий фонд гри з фішками'
challengeType: 1
forumTopicId: 301748
dashedName: problem-121-disc-game-prize-fund
---

# --description--

У торбі лежать одна червона фішка і одна синя фішка. In a game of chance a player takes a disc at random and its color is noted. Після кожного ходу фішка повертається в торбу, куди додається ще одна червона фішка, і знову потрібно навмання дістати іншу фішку.

Гравець платить £1 за гру і виграє, якщо до кінця гри дістає більше синіх фішок, ніж червоних.

Якщо гра складається з чотирьох ходів, ймовірність виграшу для гравця становить 11/120, тому максимальний призовий фонд в цьому випадку повинен складати £10, щоб не зазнати збитків. Зверніть увагу, що будь-яка виплата проводиться цілим числом фунтів стерлінгів, а також містить вартість гри в розмірі £1, тому в прикладі гравець насправді виграє £9.

Знайдіть максимальний призовий фонд, який треба виділити для однієї гри з п’ятнадцятьма ходами.

# --hints--

`discGamePrize()` має повернути `2269`.

```js
assert.strictEqual(discGamePrize(), 2269);
```

# --seed--

## --seed-contents--

```js
function discGamePrize() {

  return true;
}

discGamePrize();
```

# --solutions--

```js
// solution required
```
