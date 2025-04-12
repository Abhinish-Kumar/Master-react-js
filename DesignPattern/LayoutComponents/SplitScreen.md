SplitScreen.js

```javascript
export const SplitScreen = ({ left: Left, right: Right }) => {
  return (
    <div style={{ display: 'flex' }}>
      <div style={{ flex: 1 }}>
        <Left />
      </div>
      <div style={{ flex: 1 }}>
        <Right />
      </div>
    </div>
  );
};

```

App.js

```javascript
// App.js (or your main component file)
import React from 'react';
import { SplitScreen } from './SplitScreen';

const LeftHandComponent = () => {
  return <h1>Left!</h1>;
};

const RightHandComponent = () => {
  return <p>Right~</p>;
};

function App() {
  return (
    <SplitScreen 
      left={LeftHandComponent} 
      right={RightHandComponent} 
    />
  );
}

export default App;

```


Other example of split screen



 Ab ek aur **Split Screen** ka example lete hain – is baar ek **Product Page** jahan:

- Left side mein: 📸 **Product Image**
- Right side mein: 🛍️ **Product Details** (name, price, description, buy button)

---

### ✅ `SplitScreen.js` – Already perfect, no change:

```jsx
export const SplitScreen = ({ left: Left, right: Right }) => {
  return (
    <div style={{ display: 'flex' }}>
      <div style={{ flex: 1 }}>
        <Left />
      </div>
      <div style={{ flex: 1 }}>
        <Right />
      </div>
    </div>
  );
};
```

---

### 🎯 `App.js` – Product Showcase Example

```jsx
import React from 'react';
import { SplitScreen } from './SplitScreen';

const ProductImage = () => {
  return (
    <div style={{ padding: '1rem', backgroundColor: '#f3f4f6' }}>
      <img 
        src="https://via.placeholder.com/300"
        alt="Sample Product"
        style={{ width: '100%', borderRadius: '8px' }}
      />
    </div>
  );
};

const ProductDetails = () => {
  return (
    <div style={{ padding: '1rem', backgroundColor: '#fff7ed' }}>
      <h2>🔥 Amazing Headphones</h2>
      <p><strong>Price:</strong> ₹2999</p>
      <p>
        These wireless headphones offer crystal-clear sound, deep bass, and up to 40 hours of battery life.
      </p>
      <button 
        style={{ 
          padding: '10px 20px', 
          backgroundColor: '#34d399', 
          color: 'white', 
          border: 'none', 
          borderRadius: '5px',
          cursor: 'pointer'
        }}
      >
        Buy Now
      </button>
    </div>
  );
};

function App() {
  return (
    <SplitScreen 
      left={ProductImage} 
      right={ProductDetails} 
    />
  );
}

export default App;
```

---

### 📌 Result:
| Left: Product Image | Right: Product Description + Button |
|---------------------|--------------------------------------|
| 🎧 Image of item     | Name, ₹ Price, Desc, "Buy Now" Button |

---

### 💡 Want More Ideas?

Here are a few **cool split-screen use-cases** you can try:

| Use Case              | Left Side                 | Right Side                     |
|-----------------------|---------------------------|---------------------------------|
| Chat App              | List of conversations     | Active chat messages            |
| Dashboard             | Navigation menu           | Content area / analytics        |
| Blog layout           | Categories list            | Selected blog content           |
| Resume builder        | Form to input details     | Live preview of resume          |
| Video lesson app      | Playlist/Chapters         | Playing video + notes           |





## 🧠 **Core Idea Kya Hai?**
> React mein ek **layout component** banana jo screen ko do hisso mein baant de — Left aur Right — aur unmein hum apne khud ke components daal sakein (jaise image, product info, form, etc.).

---

## 🧱 Structure:
```jsx
<SplitScreen
  left={LeftComponent}
  right={RightComponent}
/>
```

