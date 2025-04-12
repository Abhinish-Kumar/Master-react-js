


## 🔥 SplitScreen Component — Pro Version

> "**Sirf kaam chalane ke liye nahin, ab developer ke comfort ke liye bhi sochna hai.**"

---

### 🔹 Problem: 
Pehle version me SplitScreen ke `left` aur `right` component props ke through pass ho rahe the. But iss tarah agar unme props bhejne hon, toh kaafi **boilerplate code** likhna padta hai.

---

## ✅ Step-by-Step Optimization

---

### 🎯 Step 1: **Add Flex Weights (leftWeight, rightWeight)**

**Q: Sir, Flex weight ka matlab kya hai?**  
**A:** Yeh decide karta hai ki left aur right kitna space lenge.

```jsx
<SplitScreen leftWeight={1} rightWeight={3}>
  <LeftComponent />
  <RightComponent />
</SplitScreen>
```

🔧 Inside `SplitScreen.js`:

```jsx
const Container = styled.div`
  display: flex;
`;

const Pane = styled.div`
  flex: ${(props) => props.weight};
`;

export const SplitScreen = ({
  children,
  leftWeight = 1,
  rightWeight = 1,
}) => {
  const [left, right] = children;

  return (
    <Container>
      <Pane weight={leftWeight}>{left}</Pane>
      <Pane weight={rightWeight}>{right}</Pane>
    </Container>
  );
};
```

> 💬 “Agar leftWeight = 1 aur rightWeight = 3 diya hai, toh Left pane 1/4 space lega, Right pane 3/4 space lega.”

---

### 🎯 Step 2: **Use Children Instead of Props**

Before:
```jsx
<SplitScreen left={<Left />} right={<Right />} />
```

Now (Better way):
```jsx
<SplitScreen>
  <Left name="Shaun" />
  <Right message="Hello" />
</SplitScreen>
```

⚙️ Internally:
```jsx
const [left, right] = children;
// Now directly use {left} and {right} in respective panes
```

🧠 **Why this is better:**
- Easy to pass props like `name`, `message`
- No need to tunnel props via the layout
- More intuitive
- Cleaner JSX

---

## 🧪 Dry Run:

```jsx
<SplitScreen leftWeight={2} rightWeight={1}>
  <Sidebar name="Abhinish" />
  <Main message="Welcome Back!" />
</SplitScreen>
```

- Sidebar: 2 parts
- Main: 1 part
- Result: Sidebar will take up **2/3rd**, Main will take **1/3rd**

---

## 🗃️ Summary Table

| Feature               | Old Version                           | New Version                          |
|----------------------|----------------------------------------|--------------------------------------|
| Components passing   | As `left` and `right` props            | As `children`                        |
| Weight system        | ❌ Not flexible                         | ✅ With `leftWeight`, `rightWeight`  |
| Prop forwarding      | ❌ Complex                             | ✅ Directly to child components      |
| Developer friendly   | ❌ Meh                                 | ✅ Super readable & customizable     |

---

## 💡 Bonus Tip:

> SplitScreen layout banaane ke baad, isko reusable **layout component** ki tarah treat karo. Ekbaar likh do, har jagah use karo: dashboard, profile page, etc.


# Example 




## 🎯 Real Life Use Case: **Developer Dashboard Layout**

### ✅ Features:
- Native CSS (no styled-components)
- Custom weight with `leftWeight`, `rightWeight`
- Sidebar (with menu)
- Main Content (with greeting and welcome text)

---

## 🛠 File Structure:

```
/SplitScreenApp
├── App.js
├── SplitScreen.js
├── SplitScreen.css
├── Sidebar.js
├── MainContent.js
└── index.js
```

---

### ✅ `SplitScreen.js`

```jsx
import React from 'react';
import './SplitScreen.css';

const SplitScreen = ({ children, leftWeight = 1, rightWeight = 3 }) => {
  const [left, right] = children;

  const leftStyle = {
    flex: leftWeight,
  };

  const rightStyle = {
    flex: rightWeight,
  };

  return (
    <div className="split-screen">
      <div className="pane left-pane" style={leftStyle}>
        {left}
      </div>
      <div className="pane right-pane" style={rightStyle}>
        {right}
      </div>
    </div>
  );
};

export default SplitScreen;
```

---

### ✅ `SplitScreen.css`

```css
.split-screen {
  display: flex;
  width: 100%;
  height: 100vh;
  font-family: Arial, sans-serif;
}

.pane {
  padding: 20px;
  box-sizing: border-box;
  overflow-y: auto;
}

.left-pane {
  background-color: #1e1e2f;
  color: white;
}

.right-pane {
  background-color: #f4f4f4;
  color: #333;
}
```

---

### ✅ `Sidebar.js`

```jsx
import React from 'react';

const Sidebar = ({ name }) => {
  return (
    <div>
      <h2>👨‍💻 {name}'s Dashboard</h2>
      <ul style={{ listStyle: 'none', paddingLeft: 0 }}>
        <li>📊 Overview</li>
        <li>🧠 Skills</li>
        <li>📁 Projects</li>
        <li>⚙️ Settings</li>
      </ul>
    </div>
  );
};

export default Sidebar;
```

---

### ✅ `MainContent.js`

```jsx
import React from 'react';

const MainContent = ({ message }) => {
  return (
    <div>
      <h1>{message}</h1>
      <p>Welcome to your personal developer dashboard. Stay focused, keep building! 💪</p>
      <p>This area can show charts, recent activities, project previews, etc.</p>
    </div>
  );
};

export default MainContent;
```

---

### ✅ `App.js`

```jsx
import React from 'react';
import SplitScreen from './SplitScreen';
import Sidebar from './Sidebar';
import MainContent from './MainContent';

const App = () => {
  return (
    <SplitScreen leftWeight={1} rightWeight={3}>
      <Sidebar name="Abhinish" />
      <MainContent message="Hello Abhinish!" />
    </SplitScreen>
  );
};

export default App;
```

---

### ✅ `index.js`

```jsx
import React from 'react';
import ReactDOM from 'react-dom/client';
import App from './App';
import './index.css';

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<App />);
```

---

## 🧪 Final Output

| Left Panel (Sidebar)              | Right Panel (Main Content)               |
|----------------------------------|------------------------------------------|
| - User Name                      | - Welcome Message                        |
| - Menu (Overview, Skills, etc.) | - Info, recent activity, project list    |
| Background: Dark                 | Background: Light                        |

---

## 🎉 Real-Life Use Scenarios:

✅ Admin Dashboards  
✅ Developer Portfolio Layout  
✅ CMS (Content Management System)  
✅ Project Management Tool  
✅ Learning App (Sidebar: Lessons, Right: Content)

---





