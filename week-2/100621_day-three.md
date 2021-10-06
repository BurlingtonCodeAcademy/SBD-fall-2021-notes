# Classes

A class defines a type of object and are used for making lots of objects with the same methods

```

class Circle { //circle objectr

  circumference() {

    return Math.PI * this.radius * 2;

  }

  area() {

    return Math.PI * this.radius * this.radius;

  }

}

```

Class `Circle` with a capital C is a constructor, which is a function that called when you use the `new` keyword and is the first method called on a instance.

`circle` with a lowercase c is an object.

The can be used

```

let circle = new Circle();

circle.radius = 2

circle.area()

```

the principle of Complete Construction says that after the constructor executes, the object is in a valid state

-Pass all initial values into the constructor

Encapsulation is the idea that an object should be responsible for setting its own properties.

Constructors validate your values and is one of the most valuable features in object-oriented programming because it allows you write less code and create guard clause that check for bad data

# M-E-T-H-O-D Man

**A method is a function attached to an object as a property and as JS is a dynamic language, you can add methods to any object**

Going back to the stringUtils example

- `charAt()`, `toUpperCase()`, `slice()` & `toLowerCase()` are all methods used with the `capitalize` function within the object

`this` is a method that points to object state.

``` 
let rectangle = {

    height: 10,

    width: 8,

    area: function() {

        return this.height * this.width;

    }

}

rectangle.height   //=> 10

rectangle.area()   //=> 80

```

`this.height` on the inside of the object means the same as `rectangle.height` on the outside

[speakLab](https://bootcamp.burlingtoncodeacademy.com/lessons/javascript/methods#anchor/lab_speak)

You can extend system classes by adding methods to all objects of the same type

- `String.prototype` is an object whose properties are availed to all strings

- Be careful using these types of lengthy method chaining as this will become harder to debug

Template Strings are condense simpler uses of strings

`console.log('Template Strings use backticks, which are are difficult to add in ${markdownText}')`

Methods are functions, not values.

*Beware of the difference between value and method properties*

# Object Oriented JS

## Inheritance

Classes are in fact "special functions", and just as you can define function expressions and function declarations, the class syntax has two components: class expressions and class declarations.

The constructor method is a special method of a class for creating and initializing an object of that class and by convention are capitalized `Class`

Inheritance is the mechanism of basing an object or class upon another object or class, retaining similar implementation. An inherited class is called a subclass of its parent class or super class.

`super` calls the parent's declared methods.

Inheritance works best when used to share implementation but not interface and the hierarchies are shallow (less than 3 levels)

- The `extends` keyword is used in class declarations or class expressions to create a class that is a child of another class.

"Polymorphism" -- the idea that there are many (*poly*) forms (*morphs*) that an object can take, and that several different classes of object might perform similar behavior. A general rule is to assume the an object will do what you ask until it doesn't

- Duck-typing - "If it looks like a duck, and quacks like a duck, then its a duck"

## Prototypes

Every JS object has a prototype, which work on all properties, not just functions and is a pointer to a shared constructor

If a property lookup `.` or `[]` fails, then JS recursively looks up the object's "prototype chain" until you find a property with the right name, or you reach `Object.prototype`

You can use the `instanceof` keyword to check a object's type and works on any of the classes they extend off of

If you add properties on prototypes, the appear on all objects of that type:

```

Array.prototype.sum = function() {  //Array.sum adds the elements of an array

    var total = 0;      // sets the initial value of total

    for (var i=0; i<this.length; ++i) {    //sets the elements of the array to variable name i

        total += this[i];  //then adds all the elements of the array together and resets the total variable to the sum of the array

    }

    return total; //

};

[1,2,3].sum()  // will print 6

```

```

String.prototype.reverse = function() { //String.reverse will return the string in reverse

    return this.split('').reverse().join(''); //.split(s) the string .reverse(s) everything withing the string and .join(s) it together

}

"abc".reverse() // returns "cba"

```

`apply` is a useful function that calls a function and is called on the function itself using `.`. Unlike `.bind()`, which can only be used once in a function, `apply` can be used multiple times. It als allows you to dynamically set `this` and `arguments`

# State and Machines

## What is state

State describes the status of the entire program or an individual object. It could be text, a number, a boolean, or another data type. You can use it for coordinating code. Once you update state, a bunch of different things can instantly react to that change.

## State Machines

State Machines are transitional mechanisms that allow you to move from one state to the next.

Traffic Light Example

```

let states = {    //state is what color the light is

  "green": {canChangeTo: ["yellow"]},  //green to yellow

  "yellow": {canChangeTo: ["red"]},    //yellow to red

  "red": {canChangeTo: ["green"]}      //back to green

}

let currentState = "green";  //starting state

function enterState(newState) {    //function name and argument

  let validTransitions = states[currentState].canChangeTo;  //allows transition of state to next allowable state

  if (validTransitions.includes(newState)) {   //if it can, change state

    currentState = newState;  //old state becomes new state

  } else { //guard clause against invalid transition, red cannot go back to yellow

    throw "Invalid state transition attempted - from " + currentState + " to " + newState;

  }

}

```

Why use em? 

1. Clarity

2. Predictability

3. Fail-Fast Debugging

 Lookup tables are an array that replaces runtime computation with a simpler array indexing operation. A lookup table is a table with two columns (A and B) and many rows, then given a value of A you need to find the corresponding value of B by the table.

# State and Machines

## What is state

State describes the status of the entire program or an individual object. It could be text, a number, a boolean, or another data type. You can use it for coordinating code. Once you update state, a bunch of different things can instantly react to that change.

## State Machines

State Machines are transitional mechanisms that allow you to move from one state to the next.

Traffic Light Example

```

let states = {    //state is what color the light is

  "green": {canChangeTo: ["yellow"]},  //green to yellow

  "yellow": {canChangeTo: ["red"]},    //yellow to red

  "red": {canChangeTo: ["green"]}      //back to green

}

let currentState = "green";  //starting state

function enterState(newState) {    //function name and argument

  let validTransitions = states[currentState].canChangeTo;  //allows transition of state to next allowable state

  if (validTransitions.includes(newState)) {   //if it can, change state

    currentState = newState;  //old state becomes new state

  } else { //guard clause against invalid transition, red cannot go back to yellow

    throw "Invalid state transition attempted - from " + currentState + " to " + newState;

  }

}

```

Why use em? 

1. Clarity

2. Predictability

3. Fail-Fast Debugging

 Lookup tables are an array that replaces runtime computation with a simpler array indexing operation. A lookup table is a table with two columns (A and B) and many rows, then given a value of A you need to find the corresponding value of B by the table.

# Q&A and Further Resources

## QA

- Q: What if a child class has no constructor?

    A: It will inherit the constructor and methods of its parent.

- Q: Can you only have one constructor per class?

    A: Yes, there is only one constructor per class. But there is no limitation on the constructor's complexity.

- Q: How do I comment out multiple lines of code?

    A: Highlight what you want to comment out, and press CTRL-/ (PC) or CMD-/ (Mac).

## Further Resources

- [MDN: Object Oriented JS for Beginners](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Object-oriented_JS)

- [CSS Tricks: What Is Super?](https://css-tricks.com/what-is-super-in-javascript/)

- [JS for Impatient Programmers: Prototype Chains and Supers](https://exploringjs.com/impatient-js/ch_proto-chains-classes.html)