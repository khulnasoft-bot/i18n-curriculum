---
id: 5900f4031000cf542c50ff16
title: 'Завдання 151: аркуші стандартного розміру (очікувана кількість)'
challengeType: 1
forumTopicId: 301782
dashedName: problem-151-paper-sheets-of-standard-sizes-an-expected-value-problem
---

# --description--

A printing shop runs 16 batches (jobs) every week and each batch requires a sheet of special color-proofing paper of size A5.

Щоранку в понеділок майстер відкриває новий конверт, який містить великий аркуш спеціального паперу формату A1.

Він розрізає його навпіл, таким чином отримуючи два аркуші А2. Потім він розрізає один з них навпіл, щоб отримати два аркуші А3 і так далі, поки не отримає аркуш А5, необхідний для першої партії тижня.

Усі невикористані аркуші кладуть назад у конверт.

<img alt="аркуш A1 можна поділити на A2, A3, A4 та два A5" src="https://cdn.freecodecamp.org/curriculum/project-euler/paper-sheets-of-standard-sizes-an-expected-value-problem.png" style="background-color: white; padding: 10px; display: block; margin-right: auto; margin-left: auto; margin-bottom: 1.2rem;" />

На початку кожної наступної партії він навмання бере один аркуш паперу з конверта. Якщо це А5, то майстер використовує його. Якщо ж більший, то він повторює процедуру «розрізання навпіл», поки не отримає те, що йому потрібно, а решту аркушів повертає назад до конверта.

За виключенням першої та останньої партії тижня, знайдіть очікувану кількість разів (протягом кожного тижня), коли майстер знайде в конверті один аркуш.

Дайте відповідь, заокруглену до шести знаків після коми у форматі `x.xxxxxx`.

# --hints--

`expectedValueProblem()` має повернути `0.464399`.

```js
assert.strictEqual(expectedValueProblem(), 0.464399);
```

# --seed--

## --seed-contents--

```js
function expectedValueProblem() {

  return true;
}

expectedValueProblem();
```

# --solutions--

```js
// solution required
```
