---
id: 63efdbc22a0c56070beabed7
title: 步驟-23
challengeType: 0
dashedName: step-23
---

# --description--

你已經步入正軌！ 現在，讓我們花一點時間來解決 JavaScript 中對象的一個常見問題。

當你嘗試獲取對象中不存在的屬性時，JavaScript 會返回 `undefined`。 如果你嘗試對 `undefined` 進行數學運算時，它可能會導致意外的結果，例如 `NaN`。

爲了防止這種情況，你可以使用 `||`（邏輯或） 操作符來爲它提供一個默認值。

```js
  let scores = {}; 
  let players = ["Alice", "Bob", "Charlie"];

  players.forEach(player => {
    scores[player] = scores[player] || 0;
  });
```

現在，讓我們將這個概念應用於你的 `totalCountPerProduct` 對象的 `forEach` 回調中。 請確保每一個 `dessert.id` 屬性都已經正確初始化。

使用 `||` 操作符把 `totalCountPerProduct[dessert.id]` 的默認值設置爲 `0`。

# --hints--

你應該使用點符號來訪問 `dessert` 的 `id` 屬性。

```js
const cart = new ShoppingCart();
assert.match(cart.addItem.toString(), /dessert\.id/);
```

你應該使用方括號表示法來訪問對應於 `dessert.id` 的 `totalCountPerProduct` 的屬性。

```js
const cart = new ShoppingCart();
assert.match(cart.addItem.toString(), /totalCountPerProduct\s*\[\s*dessert\.id\s*\]/);
```

你應該在表達式結尾使用 `||` 操作符將 `totalCountPerProduct[dessert.id]` 的默認值設置爲 `0`。

```js
const cart = new ShoppingCart();
assert.match(cart.addItem.toString(), /totalCountPerProduct\s*\[\s*dessert\.id\s*\]\s*=\s*totalCountPerProduct\s*\[\s*dessert\.id\s*\]\s*\|\|\s*0\s*/);
```

# --seed--

## --seed-contents--

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>freeCodeCamp Shopping Cart</title>
    <link rel="stylesheet" href="./styles.css" />
  </head>
  <body>
    <header>
      <h1 class="title">Desserts Page</h1>
    </header>
    <main>
      <button id="cart-btn" type="button" class="btn">
        <span id="show-hide-cart">Show</span> Cart
      </button>
      <div id="cart-container">
        <button class="btn" id="clear-cart-btn">Clear Cart</button>
        <div id="products-container"></div>
        <p>Total number of items: <span id="total-items">0</span></p>
        <p>Subtotal: <span id="subtotal">$0</span></p>
        <p>Taxes: <span id="taxes">$0</span></p>
        <p>Total: <span id="total">$0</span></p>
      </div>
      <div id="dessert-card-container"></div>
    </main>
    <script src="./script.js"></script>
  </body>
</html>
```

```css
*,
*::before,
*::after {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

:root {
  --dark-grey: #1b1b32;
  --light-grey: #f5f6f7;
  --black: #000;
  --white: #fff;
  --grey: #3b3b4f;
  --golden-yellow: #fecc4c;
  --yellow: #ffcc4c;
  --gold: #feac32;
  --orange: #ffac33;
  --dark-orange: #f89808;
}

body {
  background-color: var(--dark-grey);
}

.title {
  color: var(--light-grey);
  text-align: center;
  margin: 25px 0;
}

#dessert-card-container {
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  align-items: center;
}

.dessert-card {
  background-color: var(--light-grey);
  padding: 15px;
  text-align: center;
  border-radius: 15px;
  margin: 20px 10px;
}

.dessert-price {
  font-size: 1.2rem;
}

.btn {
  display: block;
  cursor: pointer;
  width: 100px;
  color: var(--dark-grey);
  background-color: var(--gold);
  background-image: linear-gradient(var(--golden-yellow), var(--orange));
  border-color: var(--gold);
  border-width: 3px;
}

.btn:hover {
  background-image: linear-gradient(var(--yellow), var(--dark-orange));
}

#cart-btn {
  position: absolute;
  top: 0;
  right: 0;
}

.add-to-cart-btn {
  margin: 30px auto 10px;
}

#cart-container {
  display: none;
  position: absolute;
  top: 60px;
  right: 0;
  background-color: var(--light-grey);
  width: 200px;
  height: 400px;
  border: 8px double var(--black);
  border-radius: 15px;
  text-align: center;
  font-size: 1.2rem;
  overflow-y: scroll;
}

.product {
  margin: 25px 0;
}

.product-count {
  display: inline-block;
  margin-right: 10px;
}

.product-category {
  margin: 10px 0;
}

@media (min-width: 768px) {
  #dessert-card-container {
    flex-direction: row;
  }

  .dessert-card {
    flex: 1 0 21%;
  }

  #cart-container {
    width: 300px;
  }
}
```

```js
const cartContainer = document.getElementById("cart-container");
const productsContainer = document.getElementById("products-container");
const dessertCards = document.getElementById("dessert-card-container");
const cartBtn = document.getElementById("cart-btn");
const clearCartBtn = document.getElementById("clear-cart-btn");
const totalNumberOfItems = document.getElementById("total-items");
const cartSubTotal = document.getElementById("subtotal");
const cartTaxes = document.getElementById("taxes");
const cartTotal = document.getElementById("total");
const showHideCartSpan = document.getElementById("show-hide-cart");
let isCartShowing = false;

const products = [
  {
    id: 1,
    name: "Vanilla Cupcakes (6 Pack)",
    price: 12.99,
    category: "Cupcake",
  },
  {
    id: 2,
    name: "French Macaron",
    price: 3.99,
    category: "Macaron",
  },
  {
    id: 3,
    name: "Pumpkin Cupcake",
    price: 3.99,
    category: "Cupcake",
  },
  {
    id: 4,
    name: "Chocolate Cupcake",
    price: 5.99,
    category: "Cupcake",
  },
  {
    id: 5,
    name: "Chocolate Pretzels (4 Pack)",
    price: 10.99,
    category: "Pretzel",
  },
  {
    id: 6,
    name: "Strawberry Ice Cream",
    price: 2.99,
    category: "Ice Cream",
  },
  {
    id: 7,
    name: "Chocolate Macarons (4 Pack)",
    price: 9.99,
    category: "Macaron",
  },
  {
    id: 8,
    name: "Strawberry Pretzel",
    price: 4.99,
    category: "Pretzel",
  },
  {
    id: 9,
    name: "Butter Pecan Ice Cream",
    price: 2.99,
    category: "Ice Cream",
  },
  {
    id: 10,
    name: "Rocky Road Ice Cream",
    price: 2.99,
    category: "Ice Cream",
  },
  {
    id: 11,
    name: "Vanilla Macarons (5 Pack)",
    price: 11.99,
    category: "Macaron",
  },
  {
    id: 12,
    name: "Lemon Cupcakes (4 Pack)",
    price: 12.99,
    category: "Cupcake",
  },
];

products.forEach(
  ({ name, id, price, category }) => {
    dessertCards.innerHTML += `
      <div class="dessert-card">
        <h2>${name}</h2>
        <p class="dessert-price">$${price}</p>
        <p class="product-category">Category: ${category}</p>
        <button 
          id="${id}" 
          class="btn add-to-cart-btn">Add to cart
        </button>
      </div>
    `;
  }
);

class ShoppingCart {
  constructor() {
    this.items = [];
    this.total = 0;
    this.taxRate = 8.25;
  }

--fcc-editable-region--
  addItem(id, products) {
    const product = products.find((item) => item.id === id);
    const { name, price } = product;
    this.items.push(product);

    const totalCountPerProduct = {};
    this.items.forEach((dessert) => {

    })
  }
--fcc-editable-region--
};
```
