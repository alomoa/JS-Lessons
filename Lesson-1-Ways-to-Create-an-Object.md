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


### Class property types
- Public
- Private
- Static
- Instance
- Field
- Getter
- Setter
- Method

#### Instance
Instance public variables can be declared anywhere in the class. It doesn't have to be only in the constructor. It can be in any function
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
#### Method

```
class MyClass{
  constructor(){
    this.method2 = () => {
      console.log("This is method 2"
    }
  }

  method1(){
    console.log("this is method 1")
  }
}

const myClass = new MyClass();

myClass.method1();
myClass.method2();
```

#### Public
Accessible outside of the class definition. Properties are public by default

#### Private
Accessible only within the class definition
Prefix the variable name with a # to make it private
Private variables must be declared at the highest level of the class

```
class MyClass{
    #foo = "bar"
    #doSomething(){
        console.log("doSomething")
    }

    constructor(){

    }

    doSomething(){
        this.#doSomething()
    }
}
```


#### Static
Properties are accessed using the class instead of an instance
Add ```static``` before the name

```
class MyClass{
  static doSomething(){
    console.log("Doing something")
  }

  static foo = "bar"
  
  constructor(){
  
  }

}

MyClass.doSomething();

console.log(MyClass.foo)

```

#### Getters and setters
Like creating a standard objects, classes can have the same getters and setters

```
class MyClass{
    _foo

    constructor(){
        this._foo = "default bar"
    }

    get foo(){
        return this._foo;
    }

    set foo(value){
        this._foo = value;
    }
}
```

### Inheritance
Classes can inherit from each other like in other languages using the ```extends``` keyword
The inheriting class' constructor must first call super() to instantiate the parent class

```
class MyClass{
    _foo
    #bar = "bar"
    constructor(){
        this._foo = "default bar"
    }

    get foo(){
        return this._foo;
    }

    set foo(value){
        this._foo = value;
    }
}

class OtherClass extends MyClass{
    constructor(){
        super()
    }
}
```


## Constructor Functions
Before classes, functions were used as a way to create a blueprint for objects. Properties of the object were declared using the dot (.) notation on "this" keyword, just like how you would in a class constructor
If you have the choice of using either classes or functions, use classes.

```
function MyClass(){
  this.foo = "bar"
  this.doSomething(){
    console.log("doing something")
  }
}

const myClass = new MyClass();

```





