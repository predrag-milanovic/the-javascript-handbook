# The DOM (Document Object Model)

Even though this handbook isn’t specifically about front-end development, it’s hard to talk about JavaScript without mentioning where it first became popular — the **browser**.

The **DOM**, or **Document Object Model**, is an in-memory representation of an HTML document.  
When you load a webpage, the browser turns the HTML code into a structured tree of objects that JavaScript can access and modify.

---

## A Quick Example

Let’s imagine we’re building a small **guild invitation page** for a game like *World of Warcraft*:

```html
<html>
  <head>
    <title>The Silver Blade Guild</title>
  </head>

  <body>
    <h1 id="mainHeading">Join the Silver Blade Guild</h1>
    <p>
      Become part of a fearless band of adventurers exploring dungeons and conquering raids.
    </p>
    <p>Meetings every Thursday at 8 PM server time.</p>
    <button id="joinButton">Join Now</button>
  </body>
</html>
```
When this HTML file is opened in the browser, the browser creates a **DOM** tree in memory.
We can interact with it using JavaScript via the global [document](https://developer.mozilla.org/en-US/docs/Web/API/Document) object.

**Accessing and Changing Elements**

Let’s say we want to change the heading text and the color of the paragraphs when a player clicks the **Join the Guild** button.

**Define the handler**
```js
function onJoinClick() {
  // We'll add DOM logic here
}
```

**Update the heading text**
```js
function onJoinClick() {
  document.getElementById("mainHeading").textContent = "Welcome to Dragonspire!"
}
```

**Modify all paragraph styles**
```js
function onJoinClick() {
  document.getElementById("mainHeading").textContent = "Welcome to Dragonspire!"
  const paragraphs = document.getElementsByTagName("p")
  for (const p of paragraphs) {
    p.style.color = "darkred"
  }
}
```

**Register the event listener**
```js
document
  .getElementById("joinButton")
  .addEventListener("click", onJoinClick)
```

Now, when the player clicks the **Join the Guild** button, the heading changes to
**“Welcome to Dragonspire!”** and the paragraphs turn dark red — all driven by DOM manipulation.