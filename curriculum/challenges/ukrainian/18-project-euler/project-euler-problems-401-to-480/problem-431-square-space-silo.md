---
id: 5900f51b1000cf542c51002e
title: 'Завдання 431: сховище квадратної форми'
challengeType: 1
forumTopicId: 302102
dashedName: problem-431-square-space-silo
---

# --description--

Фермер Фред домовляється про встановлення нового зерносховища на своїй фермі. Маючи одержимість квадратними речами, він розчаровується, коли дізнається, що нове сховище округлої форми. Квентін (представник компанії, що встановила сховище) пояснює, що компанія виробляє тільки циліндричні сховища, але зауважує, що воно має квадратний фундамент. Фреда відповідь не задовольнила і він вимагає, щоб сховище забрали із його території.

Кмітливий Квентін пояснив, що коли зерно подається згори, формується конічний схил, а кут, який утворюється із горизонтальною площиною, називається кутом природного укосу. For example if the angle of repose, $\alpha = 30°$, and grain is delivered at the center of the silo then a perfect cone will form towards the top of the cylinder. У даному сховищі, що має діаметр 6 м, приблизний обсяг невикористовуваного місця дорівнюватиме 32.648388556 м<sup>3</sup>. However, if grain is delivered at a point on the top which has a horizontal distance of $x$ metres from the center then a cone with a strangely curved and sloping base is formed. Він показав Фреду зображення.

<img alt="зображення показує процес формування ідеального конуса до вершини циліндра" src="https://cdn.freecodecamp.org/curriculum/project-euler/square-space-silo.png" style="background-color: white; padding: 10px; display: block; margin-right: auto; margin-left: auto; margin-bottom: 1.2rem;" />

Позначимо обсяг невикористовуваного місця в кубічних метрах як $V(x)$. Якщо $x = 1.114\\,785\\,284$ (зверніть увагу на три знаки в квадраті після коми), то обсяг невикористовуваного місця дорівнюватиме $V(1.114\\,785\\,284) \approx 36$. Враховуючи діапазон можливих розв’язків даного завдання, існує ще один варіант: $V(2.511\\,167\\,869) \approx 49$. Ніби квадрат є королем сховища, який засідає на зерні.

Побачивши таке чудове рішення, очі Фреда загорілися від захвату, але під час прискіпливішої перевірки креслень та підрахунків Квентіна, його радість знову перетворилась на зневіру. Фред вказав Квентіну, що саме радіус сховища, а не діаметр, дорівнює 6 м, а кут природного укосу для зерна становить 40­°. Однак, якщо Квентіну вдасться знайти множину розв’язків для цього сховища, то він із задоволенням залишить його.

Щоб кмітливий Квентін задовільнив апетит фермера Фреда до квадратних речей, потрібно визначити значення $x$ для усіх можливих об’ємів втраченого місця та обчислити $\sum x$, заокругливши до 9 знаків після коми.

# --hints--

`squareSpaceSilo()` має повернути `23.386029052`.

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
