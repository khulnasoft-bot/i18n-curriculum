---
id: 587d7b7d367417b2b2512b1d
title: for...in ステートメントによるオブジェクトのキーの繰り返し処理
challengeType: 1
forumTopicId: 301162
dashedName: iterate-through-the-keys-of-an-object-with-a-for---in-statement
---

# --description--

オブジェクト内のすべてのキーの繰り返し処理を必要とする場合があります。 You can use a <dfn>for...in</dfn> loop to do this. The for...in loop looks like:

```javascript
const refrigerator = {
  'milk': 1,
  'eggs': 12,
};

for (const food in refrigerator) {
  console.log(food, refrigerator[food]);
}
```

This code logs `milk 1`  and `eggs 12`, with each key-value pair on its own line.

We defined the variable `food` in the loop head and this variable was set to each of the object's keys on each iteration, resulting in each food's name being printed to the console.

**注:** オブジェクトも配列の場合と同じように、格納されているキーの順序は維持されません。つまり、キーを参照したりキーにアクセスしたりするときは、そのキーのオブジェクト内での位置や、表示される相対的な順序は無関係になります。

# --instructions--

関数 `countOnline` を定義しました。この関数は 1 つの引数 `allUsers` を受け取ります。 Use a <dfn>for...in</dfn> statement inside this function to loop through the `allUsers` object and return the number of users whose `online` property is set to `true`. たとえば、`countOnline` には次のようなオブジェクトが渡されます。 Each user will have an `online` property set to either `true` or `false`.

```js
{
  Alan: {
    online: false
  },
  Jeff: {
    online: true
  },
  Sarah: {
    online: false
  }
}
```

# --hints--

関数 `countOnline` では `for in` ステートメントを使用して、渡されたオブジェクトのオブジェクトキーを繰り返し処理する必要があります。

```js
assert.match(
  __helpers.removeJSComments(code),
    /for\s*\(\s*(var|let|const)\s+[a-zA-Z_$]\w*\s+in\s+[a-zA-Z_$]\w*\s*\)/
);
```

関数 `countOnline` は、オブジェクト `{ Alan: { online: false }, Jeff: { online: true }, Sarah: { online: false } }` が渡された場合、`1` を返す必要があります。

```js
const usersObj1 = {
  Alan: {
    online: false
  },
  Jeff: {
    online: true
  },
  Sarah: {
    online: false
  }
}
assert.equal(countOnline(usersObj1), 1);
```

関数 `countOnline` は、オブジェクト `{ Alan: { online: true }, Jeff: { online: false }, Sarah: { online: true } }` が渡された場合、`2` を返す必要があります。

```js
const usersObj2 = {
  Alan: {
    online: true
  },
  Jeff: {
    online: false
  },
  Sarah: {
    online: true
  }
}
assert.equal(countOnline(usersObj2), 2);
```

関数 `countOnline` は、オブジェクト `{ Alan: { online: false }, Jeff: { online: false }, Sarah: { online: false } }` が渡された場合、`0` を返す必要があります。

```js
const usersObj3 = {
  Alan: {
    online: false
  },
  Jeff: {
    online: false
  },
  Sarah: {
    online: false
  }
}
assert.equal(countOnline(usersObj3), 0);
```

# --seed--

## --seed-contents--

```js
const users = {
  Alan: {
    online: false
  },
  Jeff: {
    online: true
  },
  Sarah: {
    online: false
  }
}

function countOnline(allUsers) {
  // Only change code below this line

  // Only change code above this line
}

console.log(countOnline(users));
```

# --solutions--

```js
function countOnline(allUsers) {
  let numOnline = 0;
  for(const user in allUsers){
    if(allUsers[user].online) {
      numOnline++;
    }
  }
  return numOnline;
}
```
