# awesome-js
🦄 A curated list of javascript fundamentals for preparing interviews.

##Table of Contents
 - [Fundamentals](#fundamentals)
    - [1.1 typeof](#1.1-typeof)
    - [1.2 scope](#1.2-scope)
 - Algorithms
 - Answers
 - Credits

##Fundamentals
####1.1 typeof
<a name='1.1.1'></a>
1. What is a potential pitfall with using 
```javascript
typeof bar === "object" 
```
to determine if bar is an object? How can this pitfall be avoided?
 
[See Answer](#a1.1.1)


####1.2 scope
<a name='1.2.1'></a>
1. What will the code below output to the console and why?
```javascript
var myObject = {
    foo: "bar",
    func: function() {
        var self = this;
        console.log("outer func:  this.foo = " + this.foo);
        console.log("outer func:  self.foo = " + self.foo);
        (function() {
            console.log("inner func:  this.foo = " + this.foo);
            console.log("inner func:  self.foo = " + self.foo);
        }());
    }
};
myObject.func();
```












##Answers

####1.1 typeof
<a name='a1.1.1'></a>
1. In Javascript, ```null``` is also considered an object. Therefore, the code below surprises new developers.

```javascript
var bar = null;
console.log(typeof bar === "object"); //logs true
```

As long as one is aware of this, the problem can easily be avoided by also checking if bar is null:

````javascript
console.log((bar !== null) && (typeof bar === "object"));  // logs false
````

To be entirely thorough in our answer, there are two other things worth noting:

First, the above solution will return false if bar is a function. In most cases, this is the desired behavior, but in situations where you want to also return true for functions, you could amend the above solution to be:

```javascript
console.log((bar !== null) && ((typeof bar === "object") || (typeof bar === "function")));
```

Second, the above solution will return true if bar is an array (e.g., if var bar = [];). In most cases, this is the desired behavior, since arrays are indeed objects, but in situations where you want to also false for arrays, you could amend the above solution to be:

```javascript
console.log((bar !== null) && (typeof bar === "object") && (toString.call(bar) !== "[object Array]"));
```
[Back to Question](#1.1.1)