# Ways to create an object

There's many ways to create objects in JavaScript. I will describe 3 ways (but there are more)

## Object literal
This is the most common way that we've seen an object be created. An object literal is a way to define an object and its properties. The object wrapped in curley braces ```{}``` and each line within, separated with a comma, representing a property name and its value. 
The property name and value being separated by a colon. The value of a property can be of nay type, be it a primitive, a function, or even another object. 

```
const myObject = {
  prop1: "value",
  doSomethingProp(){
    console.log("Doing Something")
  }
}
```
### Special properties
There are two special properties, get, and set. Both of these properties have functions as values but they are not treated as such.

```
const myObject = {
  _fullName: "Muhammad Alam",
  get fullName(){
    return this._fullName
  }
  set fullName(value){
    this._fullName = value
  }
  
}

myObject.fullName //"Muhammad Alam" // get
myObject.fullName = "Tony Hawk" // set
```

The get property is executed and the value is returned when the property name attached to it is referenced ```myObject.fullName```.
The set property is executed when the value of the property name attached to it is set a new value.

Useful for logging access and adding validation

This is quite similar to the C#'s property 
```
public class Genre
{
    public string Name { get; set; }
}
```

## Classes
You know what classes are from C# so I won't go through that. I'll just go through the syntax.

### Defining & instantiation a class
```
class MyClass{
  constructor(someValue){
    this.value = someValue
  }
}

const myClass = new MyClass("Hello world")
```
Simples!

### Declaring instance variables
Instance variables can be declared anywhere in the class. It doesn't have to be only in the constructor. It can be in any function
```
class MyClass{
    constructor(){
        this.value = "hello"
        this.func()
    }

    func(){
        this.funcValue = "Funk"
    }
}
```


