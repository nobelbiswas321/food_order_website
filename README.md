# 🍽️ Feast — Food Order Website

A warm, editorial-styled food ordering web app built with vanilla HTML, CSS, and JavaScript. Browse a curated menu, add dishes to your cart, and checkout — all in a single self-contained file with no dependencies or build steps required.

---

## ✨ Features

- **Category filtering** — Browse by All, Burgers, Pizza, Sushi, Pasta, Desserts, or Drinks
- **Live search** — Filter dishes in real time by name or description
- **Dish badges** — Visual tags for 🌶 Spicy, ★ Popular, and 🌿 Veg items
- **Interactive cart** — Add items, adjust quantities, remove items dynamically
- **Order summary** — Live subtotal, delivery fee, and 8% tax calculation
- **Promo code field** — Ready for coupon/discount logic
- **Toast notifications** — Feedback on add-to-cart and checkout actions
- **One-click checkout** — Places order and clears cart with a confirmation toast
- **Responsive grid layout** — Menu adapts to available screen width

---

## 🗂️ Project Structure

```
feast/
└── index.html      # Entire app — markup, styles, and logic in one file
```

No frameworks, no bundlers, no package manager. Just open `index.html` in a browser.

---

## 🚀 Getting Started

### Run locally

```bash
# Clone or download the project
git clone https://github.com/your-username/feast.git
cd feast

# Open directly in your browser
open index.html
```

Or serve it with any static server:

```bash
# Using Python
python -m http.server 8080

# Using Node.js (npx)
npx serve .
```

Then visit `http://localhost:8080` in your browser.

---

## 🍔 Menu Data

All menu items are defined in a single `MENU` object inside the `<script>` tag:

```js
const MENU = {
  "Burgers": [
    {
      id: 1,
      name: "Smash Burger",
      desc: "Double patty, American cheese, pickles, special sauce",
      price: 12.99,
      emoji: "🍔",
      badges: ["popular"]
    },
    // ...
  ],
  // Other categories: Pizza, Sushi, Pasta, Desserts, Drinks
};
```

Each item supports the following fields:

| Field    | Type       | Description                                      |
|----------|------------|--------------------------------------------------|
| `id`     | `number`   | Unique item identifier                           |
| `name`   | `string`   | Display name of the dish                         |
| `desc`   | `string`   | Short description shown on the card              |
| `price`  | `number`   | Price in USD                                     |
| `emoji`  | `string`   | Emoji used as the dish illustration              |
| `badges` | `string[]` | Any combination of `"popular"`, `"spicy"`, `"veg"` |

---

## 🎨 Design System

| Token         | Value                          |
|---------------|--------------------------------|
| Background    | `#FDF6EC` (warm cream)         |
| Accent        | `#C2541A` (rust orange)        |
| Dark          | `#1A1208` (espresso)           |
| Gold          | `#D4A843`                      |
| Display font  | Fraunces (serif, Google Fonts) |
| Body font     | DM Sans (Google Fonts)         |

The palette is warm and editorial — designed to evoke the richness of food photography without requiring any images.

---

## 🧩 Key Functions

| Function              | Description                                          |
|-----------------------|------------------------------------------------------|
| `init()`              | Builds category tabs and renders the initial menu    |
| `renderMenu()`        | Filters and renders menu cards based on search + category |
| `addItem(id, ...)`    | Adds an item to the cart or increments its quantity  |
| `changeQty(id, d)`    | Increments or decrements a cart item's quantity      |
| `renderCart()`        | Re-renders the sidebar cart and recalculates totals  |
| `checkout()`          | Simulates order placement and resets the cart        |
| `showToast(msg)`      | Displays a temporary notification at the bottom      |

---

## 🔧 Customisation

**Add a new category:**
Add a new key to the `MENU` object with an array of item objects.

**Change delivery fee or tax rate:**
In `renderCart()`, update the `delivery` variable or the `0.08` tax multiplier.

**Connect to a real backend:**
Replace the `checkout()` function with a `fetch()` call to your API endpoint, passing the current `cart` object as the request body.

**Add real images:**
Replace the `.food-img` emoji `<div>` in `renderMenu()` with an `<img>` tag pointing to your image URLs.

---

## 📦 Dependencies

| Resource      | Source         | Purpose              |
|---------------|----------------|----------------------|
| Fraunces      | Google Fonts   | Display / heading font |
| DM Sans       | Google Fonts   | Body / UI font       |

No JavaScript libraries or frameworks are used. Everything else is vanilla.

---

## 📄 License

MIT — free to use, modify, and distribute.
