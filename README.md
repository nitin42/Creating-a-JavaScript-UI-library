**WORK IN PROGRESS**

# Creating-a-JavaScript-UI-library
> This is a tutorial for creating a JavaScript UI library.

## Introduction

In this tutorial, we will be creating a JavaScript UI library in which views will be updated with corresponding changes to the model. Our main goal is to learn how views are updated with changes to model, how different hooks are called and managed internally throughout the lifecycle of the view. I hope you will come up with a solid intiution of how the real UI libraries work and evolve.

Our library will be named after ***Elmo***, a Muppet character!

## Who should read this tutorial ?

This tutorial is for casual programmers who just want to learn how to create a basic UI library.

## Syntax

**HTML**

```html
<body>
   <div id="example">
     <span var="units" /> Units
     <span var="price" class="Drag" min-data="2" max-data="10"> $</span>
   </div>
</body>
```

**JS**

```js
const { Elmo } = require("elmo-ui")

const root = document.getElementById("example")

const models = {
  onInitialise: () => {
    this.units = 10;
    this.price = 50;
    this.offset = 5;
  },
  onUpdate: () => {
    this.price = this.price * this.offset
  }
}

const inst = new Elmo(root, models)
```

What are those weird attributes `var`, `min-data` and `max-data` ? Don't worry, we will cover the syntax and the implementation in detail later.

## Table of contents
