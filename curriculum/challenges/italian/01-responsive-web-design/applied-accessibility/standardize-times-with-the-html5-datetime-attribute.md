---
id: 587d778c367417b2b2512aa9
title: Standardizzare gli orari con l'attributo HTML5 datetime
challengeType: 0
videoUrl: 'https://scrimba.com/c/cmzMgtz'
forumTopicId: 301025
dashedName: standardize-times-with-the-html5-datetime-attribute
---

# --description--

Continuing with the date theme, HTML5 also introduced the `time` element along with a `datetime` attribute to standardize times. The `time` element is an inline element that can wrap a date or time on a page. A `datetime` attribute holds a valid format of that date. This is the value accessed by assistive devices. It helps avoid confusion by stating a standardized version of a time, even if it's informally or colloquially written in the text.

Ecco un esempio:

```html
<p>Master Camper Cat officiated the cage match between Goro and Scorpion <time datetime="2013-02-13">last Wednesday</time>, which ended in a draw.</p>
```

# --instructions--

I risultati del sondaggio di Camper Cat sul torneo di Mortal Kombat sono arrivati! Metti un tag `time` intorno al testo `Thursday, September 15<sup>th</sup>` e aggiungi un attributo `datetime` impostato a `2016-09-15`.

# --before-all--

```js
const getTimeElement = () => {
  const pElement = [...document.querySelectorAll("article > p")]
  .filter(x => x?.textContent?.includes("Thank you to everyone for responding to Master Camper Cat's survey."));

  return pElement[0] ? pElement[0].querySelector("time") : null;
};

const getDatetimeAttr = () => {
  const timeElement = getTimeElement();
  return timeElement?.getAttribute("datetime");
};
```

# --hints--

Il tuo codice dovrebbe avere un elemento `p` che include il testo `Thank you to everyone for responding to Master Camper Cat's survey.` e che abbia un elemento `time`.

```js
assert.exists(getTimeElement());
```

I tuoi tag `time` aggiuntivi dovrebbero avvolgere il testo `Thursday, September 15<sup>th</sup>`.

```js
assert.strictEqual(getTimeElement()?.innerHTML?.trim(), 'Thursday, September 15<sup>th</sup>');
```

Il tuo tag `time` dovrebbe avere un attributo `datetime` non vuoto.

```js
assert(getDatetimeAttr()?.length != 0);
```

Il tuo attributo `datetime` dovrebbe essere impostato sul valore `2016-09-15`.

```js
assert.equal(getDatetimeAttr() , '2016-09-15');
```

# --seed--

## --seed-contents--

```html
<body>
  <header>
    <h1>Tournaments</h1>
  </header>
  <article>
    <h2>Mortal Kombat Tournament Survey Results</h2>

    <!-- Only change code below this line -->

    <p>Thank you to everyone for responding to Master Camper Cat's survey. The best day to host the vaunted Mortal Kombat tournament is Thursday, September 15<sup>th</sup>. May the best ninja win!</p>

    <!-- Only change code above this line -->

    <section>
      <h3>Comments:</h3>
      <article>
        <p>Posted by: Sub-Zero on <time datetime="2016-08-13T20:01Z">August 13<sup>th</sup></time></p>
        <p>Johnny Cage better be there, I'll finish him!</p>
      </article>
      <article>
        <p>Posted by: Doge on <time datetime="2016-08-15T08:12Z">August 15<sup>th</sup></time></p>
        <p>Wow, much combat, so mortal.</p>
      </article>
      <article>
        <p>Posted by: The Grim Reaper on <time datetime="2016-08-16T00:00Z">August 16<sup>th</sup></time></p>
        <p>Looks like I'll be busy that day.</p>
      </article>
    </section>
  </article>
  <footer>&copy; 2018 Camper Cat</footer>
</body>
```

# --solutions--

```html
<body>
  <header>
    <h1>Tournaments</h1>
  </header>
  <article>
    <h2>Mortal Kombat Tournament Survey Results</h2>

    <p>Thank you to everyone for responding to Master Camper Cat's survey. The best day to host the vaunted Mortal Kombat tournament is <time datetime="2016-09-15">Thursday, September 15<sup>th</sup></time>. May the best ninja win!</p>

    <section>
      <h3>Comments:</h3>
      <article>
        <p>Posted by: Sub-Zero on <time datetime="2016-08-13T20:01Z">August 13<sup>th</sup></time></p>
        <p>Johnny Cage better be there, I'll finish him!</p>
      </article>
      <article>
        <p>Posted by: Doge on <time datetime="2016-08-15T08:12Z">August 15<sup>th</sup></time></p>
        <p>Wow, much combat, so mortal.</p>
      </article>
      <article>
        <p>Posted by: The Grim Reaper on <time datetime="2016-08-16T00:00Z">August 16<sup>th</sup></time></p>
        <p>Looks like I'll be busy that day.</p>
      </article>
    </section>
  </article>
  <footer>&copy; 2018 Camper Cat</footer>
</body>
```
