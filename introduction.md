## Introduction

Welcome to the first part of the tutorial. In this part, we will discuss about what we are going to do. So we will be creating a basic UI library which will render the views on requiring changes to the model. 

**Creating a model**

The code for a model could like so:

```js
function onInitialise() {
  this.value = 10
  this.units = 5 // Initial value
  this.factor = 40
}

function onUpdate(self) {
  self.setState(this.units, this.value * this.factor)
}

const model = {
  onInitialise,
  onUpdate
}
```

**Creating a simple view**

Let's imagine how a view could look like.

```html
<div id="example">
  <span var="units" > Units
</div>
```

The attribute `var` is used to declare a variable that will be updated and rendered by our library. You can see that we have initialised its value in the function `onInitialise` to `5`. When the view will be rendered, its value will be updated to `400`. We can compare this view to a template like syntax.

```html
<span>{{ units }}</span>
```

**Updating models**

You can see that in the function `onUpdate` we use `self.setState` to update our variables declared in view. `setState` will attempt to update the variable only if its values has been changed else it will skip the update.

Here `self` is the instance of our class `Elmo` which we will be creating in the later parts of our tutorial.