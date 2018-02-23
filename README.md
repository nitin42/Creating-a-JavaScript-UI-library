**WORK IN PROGRESS**

# Creating-a-JavaScript-UI-library
> This is a tutorial for creating a JavaScript UI library.

## Introduction

In this tutorial, we will be creating a JavaScript UI library in which views will be updated with corresponding changes to the model. Our main goal is to learn how views are updated with changes to model, how different hooks are called and managed internally throughout the lifecycle of the view. I hope you will come up with a solid intiution of how the real UI libraries work and evolve.

Our library will be named after ***Elmo***, a Muppet character!

> Sorry, I am bad with naming things.

**Note** - This, however, may not serve as a complete source for creating a UI library because we will be adding some more things on top of it (custom UI components provided by the library) which is completely different. But I am sure you will enjoy reading this tutorial.

## Who should read this tutorial ?

This tutorial is for casual programmers who just want to learn how to create a UI library.

## Syntax

**HTML**

```html
<body>
   <div id="example">
     <span var="units" /> Units
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

Although I wanted to go for a template syntax for rendering the views but settled for the custom attributes for the sake of simplicity.

## Table of contents

* [Introduction]()
* [Structuring API]()
* [Creating models]()
* [Defining hooks]()
* [Traversing the children]()
* [Creating views from classnames and variables]()
* [Parsing attributes]()
* [Defining strategies for updating the views]()
* [Getters and setters for template variables]()
* [Optimisation]()

## I have read the whole tutorial and I didn't enjoyed reading it.

No issues. I am not an expert in creating UI libraries and I am just sharing what I've learned. But I'm glad that you gave a try.

## This tutorial was good. I enjoyed reading it!

Thanks! You can spread a word about it on Twitter. I am at [NTulswani](https://twitter.com/NTulswani).

## Suggestions to improve the tutorial

May be create an issue ?
