---
id: 5dfb5ecbeacea3f48c6300b1
title: Крок 23
challengeType: 0
dashedName: step-23
---

# --description--

Елемент `li` використовують, щоб створити елемент з впорядкованого чи невпорядкованого списку.

Ось приклад елементів невпорядкованого списку:

```html
<ul>
  <li>milk</li>
  <li>cheese</li>
</ul>
```

Вкладіть три елементи списку до `ul`, перерахувавши три речі, які люблять коти:

`catnip`

`laser pointers`

`lasagna`

# --hints--

Ви повинні мати три елементи `li`. Кожен елемент `li` повинен мати власні початковий та кінцевий теги.

```js
assert.lengthOf(document.querySelectorAll('li'), 3);
assert.lengthOf(code.match(/<\/li\>/g), 3);
```

У вас мають бути три елементи `li` з текстом `catnip`, `laser pointers` та `lasagna` у будь-якому порядку. Ви або не написали текст, або маєте друкарську помилку.

```js
assert.deepStrictEqual(
  [...document.querySelectorAll('li')]
    .map((item) => item.innerText.toLowerCase())
    .sort((a, b) => a.localeCompare(b)),
  ['catnip', 'lasagna', 'laser pointers']
);
```

Три елементи `li` мають бути між початковим та кінцевим тегами елемента `ul`.

```js
assert.lengthOf(
  [...document.querySelectorAll('li')].filter(
    (item) => item.parentNode.nodeName === 'UL'
  ), 3
);
```

# --seed--

## --seed-contents--

```html
<html>
  <body>
    <main>
      <h1>CatPhotoApp</h1>
      <section>
        <h2>Cat Photos</h2>
        <p>Everyone loves <a href="https://cdn.freecodecamp.org/curriculum/cat-photo-app/running-cats.jpg">cute cats</a> online!</p>
        <p>See more <a target="_blank" href="https://freecatphotoapp.com">cat photos</a> in our gallery.</p>
        <a href="https://freecatphotoapp.com"><img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back."></a>
      </section>
      <section>
        <h2>Cat Lists</h2>
        <h3>Things cats love:</h3>
--fcc-editable-region--
        <ul>

        </ul>
--fcc-editable-region--
      </section>
    </main>
  </body>
</html>
```
