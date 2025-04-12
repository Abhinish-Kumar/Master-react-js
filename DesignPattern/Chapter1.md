# What are Design Patterns?
Design patterns are effective solutions to common application deveopement challenges. 
Design patterns are used in different contest , like OOP design patterns. 
We are not learning about the  design patterns of OOP.
The patterns we cover here are effective solutions to some extremely common challenges in React.

## Common Challenges 

- Creating reusable layouts.
- Reusing complex logic between multiple components.
- Working with forms.
- Incorporate funcitonal concepts into our code.



Design pattern :- ise shortcut jo developer ne khud ke kaam ko asaan banane ke liye create kiya hai(effective solutions to common problems)


## 🟨 What is a Design Pattern?

> ✍️ **Definition**: "Design patterns are **effective solutions** to **common challenges** in application development."

- **Effective** word pe focus karo! Har solution design pattern nahi hota.
- Jo code ko **clean, maintainable aur reusable** banaye – wahi **pattern** kehlata hai.
- Jo galtiyaan karwa de – usko kehte hain **anti-pattern**.

---

### ❌ Anti-pattern ka Example:  
Tumne form banaya React mein, har input ka `useState` banake 10 line ka code likh diya, fir dusra form mein wahi kaam repeat – **copy paste**.  
Yeh galat hai bhai – agar 4 form aagaye toh 40 states ban jayengi. This is an **anti-pattern** – galat approach.

---

## 🧩 React ke Design Patterns kis type ke honge?

Yahan pe instructor clear kar rahe hain:

- Gang of Four = Creational, Behavioral, Structural – yeh sab **Java, C++ jaise OOP languages** ke liye hota hai.
- React mein hum **component-based UI** banate hain – toh design patterns bhi UI aur logic reuse ke around honge.

---

## 🔍 Real-Life React Problems (Jinpe Pattern Lagta Hai):

1. **Reusable Layouts**:
   - Header, Footer, Sidebar ko har page mein kaise reuse karein?
   - Example: `Layout` component bana ke use karna har page mein.
   - Isse kehte hain **Layout Pattern**.

2. **Complex Logic Reuse**:
   - 2 components ko server se data fetch karna hai – logic repeat mat karo!
   - Iske liye use karte hain **Custom Hooks Pattern**.

3. **Forms in React**:
   - Forms mein `useState` + `onChange` likhte likhte thak jaate ho?
   - Uske liye hota hai **Controlled/Uncontrolled Forms Pattern**, aur `react-hook-form` jaisi library ka use.

4. **Functional Programming Concepts**:
   - **Pure functions, immutability, map, filter, reduce** – inko kaise React ke components mein integrate karein?
   - Yeh hota hai **Functional Component Patterns**.

---

## 🎯 Goal of React Design Patterns:

> "Code ko smart banao, short banao, aur baar baar use hone layak banao."

React ke har application mein kuch challenges baar baar aate hain:
- Same layout repeat hota hai
- Same data fetching logic hota hai
- Form handle karna hota hai
- State manage karni hoti hai

Toh agar har developer ne apna jugad banaya, toh project ka kya hoga?
> **"Design pattern ek proven jugad hai jo already test ho chuka hai."**

---

## 🔁 Summary Table – React Design Patterns Introduction

| Topic                         | Explanation                                                  |
|------------------------------|--------------------------------------------------------------|
| Design Pattern               | Effective solution to common app challenges                 |
| Anti-pattern                 | Ineffective solution – makes code complex & hard to manage  |
| Not OOP Patterns             | Yeh React ke practical UI/logic problems ko solve karta hai |
| Reusable Layout              | Ek `Layout` component bana ke har page mein use karo         |
| Complex Logic Reuse         | `Custom Hooks` banao – logic ko ek jagah likho              |
| Form Handling               | Best practices + libraries (`react-hook-form`, etc.)         |
| Functional Programming      | Pure functions, map, filter – FP concepts React mein         |

---


> "Toh bhaiya, React ka design pattern matlab shortcut jaisa nahi hai – yeh ek *smart engineering solution* hai jo time bachata hai, bugs kam karta hai, aur future mein code ko samajhna easy banata hai."





