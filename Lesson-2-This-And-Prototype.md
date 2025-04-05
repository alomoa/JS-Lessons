
## Prototype
Prototype is the mechanism by which objects inherit from other objects.

Created objects have their properties (as they do) but you can see there are other properties. Those properties are from the object's prototype.
Every object has a property called prototype, which is an object itself so it also has a protoype property and so on. This is called the prototype chain, and at the end of the chain is null.

When a property is looked up, it is first searched for in the object itself. If the property is not found in the object, it's then searched for in the protoype and then the prototype's prototype, and so on.

Objects by default have the prototype Obect.protoype. Complex data structures (date, array), have different prototypes but have Object.prototype later down the chain. That's where methods like array.map, array.filter, date.getTime comes from: the prototype!

```
const obj = {}

obj -> Object.prototype -> null
```

### Own Property
We now know that objects have more than just the properties that were defined, they also inherit properties from their prototypes. Properties that are defines on the object itself are referred to as own property

## This (Execution context)

This refers the to context or environment code is executed in. At the top level, code is executed in the global context. Meaning that this will point to window for browsers or global for Nodejs.
A function's execution context can vary depending on where it is executed. If it's executed outside of an object, then the execution context is global. If it's called through an object, then the execution context is the object itself.

```
doSomething() //this = window

obj.doSomething()//this = obj
```

Other ways to set the execution context are:
- fn.call(context) -> doSomething.call(obj) - Calls a function passing a specific context to execute in
- fn.bind(context) -> doSomething.bind(obj) - Returns an function that will always be called with the specified context


### Functions vs arrow functions
Functions take on the context that they're executed in whlie arrow functions preserve the context that they were created in

```
function doSomething(){
  console.log(this)
}

const doSomethingArrow = () => console.log(this)

const obj = {
  doSomething: doSomething,
  doSomethingArrow: doSomethingArrow
}

obj.doSomething() // this = obj
obj.doSomethingArrow() // this = window
```

