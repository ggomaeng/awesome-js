# awesome-js
🦄 A curated list of javascript fundamentals for preparing interviews.

##Table of Contents
- [Fundamentals](#fundamentals)
    - [1.1 - Typeof](#1.1)
    - [1.2 - Scope](#1.2)
    - [1.3 - Error Handling](#1.3)
    - [1.4 - Numbers](#1.4)
    - [1.5 - Events and Timing](#1.5)
    - [1.6 - Functions](#1.6)
    - [1.7 - Reference](#1.7)
    - [1.8 - Comparison and Logical Operators](#1.8)
    - [1.9 - Objects](#1.9)
    - [1.10 - DOM](#1.10)
    - [1.11 - Prototype](#1.11)
- [Algorithms](#algorithms)
    - [2.1 - String Palindrome](#2.1)
    - [2.2 - Square Root](#2.2)
    - [2.3 - Flattening Array](#2.3) 
    - [2.4 - Reordering Objects in an Array](#2.4) 
    - [2.5 - Replacing Substring](#2.5) 
    - [2.6 - Move Zeroes](#2.6) 
- [Answers](#answers)
- [Credits](#credits)

##Fundamentals
<a name='1.1'/>

### 1.1 typeof  

<a name='1.1.1'/>

#### 1.1.1

What is a potential pitfall with using 

```javascript
typeof bar === "object" 
```
to determine if bar is an object? How can this pitfall be avoided?

[See Answer](#a1.1.1)

-----

<a name='1.1.2'/>

#### 1.1.2

What is `NaN`? What is its type? How can you reliably test if a value is equal to `NaN`?

[See Answer](#a1.1.2)

-------

<a name='1.1.3'/>

#### 1.1.3

What will the code below output to the console and why ?

```javascript
console.log(1 +  "2" + "2");
console.log(1 +  +"2" + "2");
console.log(1 +  -"1" + "2");
console.log(+"1" +  "1" + "2");
console.log( "A" - "B" + "2");
console.log( "A" - "B" + 2);
```

[See Answer](#a1.1.3)

------

<a name='1.1.4'/>

#### 1.1.4

What's the difference between using “let” and “var” to declare a variable?

[See Answer](#a1.1.4)

----

<a name='1.2'/>

### 1.2 scope 

<a name='1.2.1'/>
#### 1.2.1

What will the code below output to the console and why?

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

[See Answer](#a1.2.1)

------

<a name='1.2.2'/>

#### 1.2.2

What is the significance of, and reason for, wrapping the entire content of a JavaScript source file in a function block?

[See Answer](#a1.2.2)

-------

<a name='1.2.3'/>

#### 1.2.3

Consider the following code snippet:

```javascript
for (var i = 0; i < 5; i++) {
  var btn = document.createElement('button');
  btn.appendChild(document.createTextNode('Button ' + i));
  btn.addEventListener('click', function(){ console.log(i); });
  document.body.appendChild(btn);
}
```

(a) What gets logged to the console when the user clicks on “Button 4” and why?

(b) Provide one or more alternate implementations that will work as expected.

[See Answer](#a1.2.3)

-----

<a name='1.2.4'/>

#### 1.2.4

What is a “closure” in JavaScript? Provide an example.

[See Answer](#a1.2.4)

-----

<a name='1.2.5'/>

#### 1.2.5

What will be the output of the following code:

```javascript
for (var i = 0; i < 5; i++) {
  setTimeout(function() { console.log(i); }, i * 1000 );
}
```

Explain your answer. How could the use of closures help here?

[See Answer](#a1.2.5)

-----

<a name='1.2.6'/>

#### 1.2.6

Consider the code snippet below. What will the console output be and why?

```javascript
(function(x) {
    return (function(y) {
        console.log(x);
    })(2)
})(1);
```

[See Answer](#a1.2.6)

------

<a name='1.2.7'/>

#### 1.2.7

What will the following code output to the console and why:

```javascript
var hero = {
    _name: 'John Doe',
    getSecretIdentity: function (){
        return this._name;
    }
};

var stoleSecretIdentity = hero.getSecretIdentity;

console.log(stoleSecretIdentity());
console.log(hero.getSecretIdentity());
```

What is the issue with this code and how can it be fixed.

[See Answer](#a1.2.7)

-----

<a name='1.3'/>

### 1.3 Error Handling 

<a name='1.3.1'/>

#### 1.3.1

What is the significance, and what are the benefits, of including `'use strict'` at the beginning of a JavaScript source file?

[See Answer](#a1.3.1)

-----------

<a name='1.3.2'/>

#### 1.3.2

Consider the two functions below. Will they both return the same thing? Why or why not?

```javascript
function foo1()
{
  return {
      bar: "hello"
  };
}

function foo2()
{
  return
  {
      bar: "hello"
  };
}
```

[See Answer](#a1.3.2)

------

<a name='1.3.3'/>

#### 1.3.3

The following recursive code will cause a stack overflow if the array list is too large. How can you fix this and still retain the recursive pattern?

```javascript
var list = readHugeList();

var nextListItem = function() {
    var item = list.pop();

    if (item) {
        // process the list item...
        nextListItem();
    }
};
```

[See Answer](#a1.3.3)

---------

<a name='1.4'/>

### 1.4 Numbers 

<a name='1.4.1'/>

#### 1.4.1

What will the code below output? Explain your answer.

```javascript
console.log(0.1 + 0.2);
console.log(0.1 + 0.2 == 0.3);
```

[See Answer](#a1.4.1)

-----

#### 1.4.2

Discuss possible ways to write a function `isInteger(x)` that determines if `x` is an integer.

[See Answer](#a1.4.2)

-----

<a name='1.5'/>

### 1.5 Events and Runtime

<a name='1.5.1'/>

#### 1.5.1

In what order will the numbers 1-4 be logged to the console when the code below is executed? Why?

```javascript
(function() {
    console.log(1); 
    setTimeout(function(){console.log(2)}, 1000); 
    setTimeout(function(){console.log(3)}, 0); 
    console.log(4);
})();
```

[See Answer](#a1.5.1)

-----

<a name='1.6'/>

### 1.6 Functions

<a name='1.6.1'/>

#### 1.6.1

Write a `sum` method which will work properly when invoked using either syntax below.

```javascript
console.log(sum(2,3));   // Outputs 5
console.log(sum(2)(3));  // Outputs 5
```

[See Answer](#a1.6.1)

------

<a name='1.6.2'/>

#### 1.6.2

What will the following code output to the console:

```javascript
console.log((function f(n){return ((n > 1) ? n * f(n-1) : n)})(10));
```

Explain your answer.

[See Answer](#a1.6.2)

----

<a name='1.7'/>

### 1.7 Reference

<a name='1.7.1'/>

#### 1.7.1

What will the code below output to the console and why?

```javascript
var arr1 = "john".split('');
var arr2 = arr1.reverse();
var arr3 = "jones".split('');
arr2.push(arr3);
console.log("array 1: length=" + arr1.length + " last=" + arr1.slice(-1));
console.log("array 2: length=" + arr2.length + " last=" + arr2.slice(-1));
```

[See Answer](#a1.7.1)

-------

<a name='1.8'/>

### 1.8 Comparison and Logical Operators

<a name='1.8.1'/>

#### 1.8.1

What would the following lines of code output to the console?

```javascript
console.log("0 || 1 = "+(0 || 1));
console.log("1 || 2 = "+(1 || 2));
console.log("0 && 1 = "+(0 && 1));
console.log("1 && 2 = "+(1 && 2));
```

Explain your answer.

[See Answer](#a1.8.1)

----

<a name='1.8.2'/>

#### 1.8.2

What will be the output when the following code is executed? Explain.

```javascript
console.log(false == '0')
console.log(false === '0')
```

[See Answer](#a1.8.2)

------

<a name='1.9'/>

### 1.9 Objects

<a name='1.9.1'/>

#### 1.9.1

What is the output out of the following code? Explain your answer.

```javascript
var a={},
    b={key:'b'},
    c={key:'c'};

a[b]=123;
a[c]=456;

console.log(a[b]);
```

[See Answer](#a1.9.1)

------

<a name='1.9.2'/>

#### 1.9.2

Compare and contrast objects and hashtables in JavaScript.

[See Answer](#a1.9.2)

------

<a name='1.10'/>

### 1.10 DOM (Document Object Model)

<a name='1.10.1'/>

#### 1.10.1

Create a function that, given a DOM Element on the page, will visit the element itself and *all* of its descendents (*not just its immediate children*). For each element visited, the function should pass that element to a provided callback function.

The arguments to the function should be:

- a DOM element
- a callback function (that takes a DOM element as its argument)

[See Answer](#a1.10.1)

----------

<a name='1.11'/>

### 1.11 Prototype

<a name='1.11.1'/>

#### 1.11

Describe inheritance and the prototype chain in JavaScript. Give an example.

[See Answer](#a1.11.1)

--------







## Algorithms

<a name='2.1'/>

#### 2.1 String Palindrome

Write a simple function (less than 80 characters) that returns a boolean indicating whether or not a string is a [palindrome](http://www.palindromelist.net/).

[See Answer](#a2.1)

---------

<a name='2.2'/>

#### 2.2 Square Root

Manually calculate the square root of a number with Javascript

[See Answer](#a2.2)

------

<a name='2.3'/>

#### 2.3 Flattening Arrays

Can you write a function that deeply flattens an array?

```javascript
//example
input = [0, 1, [2, 3], [[4, [5]]]];
output = [0, 1, 2, 3, 4, 5];
```

[See Answer](#a2.3)

---

<a name='2.4'/>

#### 2.4 Reordering Objects in an Array

We have an array of objects A and an array of indexes B. Reorder objects in array A with given indexes in array B. Do not change array A's length. 

```javascript
//example
var A = [C, D, E, F, G];
var B = [3, 0, 4, 1, 2];

sort(A, B);
// A is now [D, F, G, C, E];
```

[See Answer](#a2.4)

----

<a name='2.5'/>

#### 2.5 Replacing Substring

Given a string Sting="ABCSC" Check whether it contains a Substring="ABC"?

1) If no , return "-1". 

2) If yes , remove the substring from string and return "SC". 

[See Answer](#a2.5)

------

<a name='2.6'/>

#### 2.6 Move Zeroes

Given an array `nums`, write a function to move all `0`'s to the end of it while maintaining the relative order of the non-zero elements.

For example, given `nums = [0, 1, 0, 3, 12]`, after calling your function, `nums` should be `[1, 3, 12, 0, 0]`.

**Note**:

1. You must do this **in-place** without making a copy of the array.
2. Minimize the total number of operations.

[See Answer](#a2.6)

---------



##Answers

### 1.1 typeof

<a name='a1.1.1'/>

#### 1.1.1

In Javascript, ```null``` is also considered an object. Therefore, the code below surprises javascript newcomers.

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

----

<a name='a1.1.2'/>

#### 1.1.2

The `NaN` property represents a value that is “not a number”. This special value results from an operation that could not be performed either because one of the operands was non-numeric (e.g., `"abc" / 4`), or because the result of the operation is non-numeric (e.g., an attempt to divide by zero).

While this seems straightforward enough, there are a couple of somewhat surprising characteristics of `NaN` that can result in hair-pulling bugs if one is not aware of them.

For one thing, although `NaN` means “not a number”, its type is, believe it or not, `Number`:

```javascript
console.log(typeof NaN === "number");  // logs "true"
```

Additionally, `NaN` compared to anything – even itself! – is false:

```javascript
console.log(NaN === NaN);  // logs "false"
```

A *semi-reliable* way to test whether a number is equal to NaN is with the built-in function `isNaN()`, but even using [`isNaN()` is an imperfect solution](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/isNaN#Confusing_special-case_behavior).

A better solution would either be to use `value !== value`, which would *only* produce true if the value is equal to NaN. Also, ES6 offers a new [`Number.isNaN()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/isNaN) function, which is a different and more reliable than the old global `isNaN()` function.

[Back to Question](#1.1.2)

-----

<a name='a1.1.3'/>

#### 1.1.3

The above code will output the following to the console:

```javascript
"122"
"32"
"02"
"112"
"NaN2"
NaN
```

Here’s why…

The fundamental issue here is that JavaScript (ECMAScript) is a loosely typed language and it performs automatic type conversion on values to accommodate the operation being performed. Let’s see how this plays out with each of the above examples.

**Example 1:** `1 + "2" + "2"` **Outputs:** `"122"` **Explanation:** The first operation to be performed in `1 + "2"`. Since one of the operands (`"2"`) is a string, JavaScript assumes it needs to perform string concatenation and therefore converts the type of `1` to `"1"`, `1 + "2"` yields `"12"`. Then, `"12" + "2"` yields `"122"`.

**Example 2:** `1 + +"2" + "2"` **Outputs:** `"32"` **Explanation:** Based on order of operations, the first operation to be performed is `+"2"` (the extra `+` before the first `"2"` is treated as a unary operator). Thus, JavaScript converts the type of `"2"` to numeric and then applies the unary `+` sign to it (i.e., treats it as a positive number). As a result, the next operation is now `1 + 2` which of course yields `3`. But then, we have an operation between a number and a string (i.e., `3` and `"2"`), so once again JavaScript converts the type of the numeric value to a string and performs string concatenation, yielding `"32"`.

**Example 3:** `1 + -"1" + "2"` **Outputs:** `"02"` **Explanation:** The explanation here is identical to the prior example, except the unary operator is `-` rather than `+`. So `"1"` becomes `1`, which then becomes `-1` when the `-` is applied, which is then added to `1` yielding `0`, which is then converted to a string and concatenated with the final `"2"` operand, yielding `"02"`.

**Example 4:** `+"1" + "1" + "2"` **Outputs:** `"112"` **Explanation:** Although the first `"1"` operand is typecast to a numeric value based on the unary `+` operator that precedes it, it is then immediately converted back to a string when it is concatenated with the second `"1"` operand, which is then concatenated with the final `"2"` operand, yielding the string `"112"`.

**Example 5:** `"A" - "B" + "2"` **Outputs:** `"NaN2"` **Explanation:** Since the `-` operator can not be applied to strings, and since neither `"A"` nor `"B"` can be converted to numeric values, `"A" - "B"` yields `NaN` which is then concatenated with the string `"2"` to yield “NaN2”.

**Example 6:** `"A" - "B" + 2` **Outputs:** `NaN` **Explanation:** As exlained in the previous example, `"A" - "B"` yields `NaN`. But any operator applied to NaN with any other numeric operand will still yield `NaN`.

[Back to Question](#1.1.3)

-------

<a name='a1.1.4'/>

#### 1.1.4

The difference is scoping. `var` is scoped to the nearest function block and `let` is scoped to the nearest *enclosing* block (both are global if outside any block), which can be smaller than a function block.

Also, variables declared with `let` are not accessible before they are declared in their enclosing block.

### Global:

They are very similar when used like this outside a function block.

```javascript
let me = 'go';  // globally scoped
var i = 'able'; // globally scoped
```

However, global variables defined with `let` will not be added as properties on the global `window`object like those defined with `var`.

```javascript
console.log(window.me); // undefined
console.log(window.i); // 'able'
```

### Function:

They are identical when used like this in a function block.

```javascript
function ingWithinEstablishedParameters() {
    let terOfRecommendation = 'awesome worker!'; //function block scoped
    var sityCheerleading = 'go!'; //function block scoped
}
```

### Block:

Here is the difference. `let` is only visible in the `for()` loop and `var` is visible to the whole function.

```javascript
function allyIlliterate() {
    //tuce is *not* visible out here

    for( let tuce = 0; tuce < 5; tuce++ ) {
        //tuce is only visible in here (and in the for() parentheses)
        //and there is a separate tuce variable for each iteration of the loop
    }

    //tuce is *not* visible out here
}

function byE40() {
    //nish *is* visible out here

    for( var nish = 0; nish < 5; nish++ ) {
        //nish is visible to the whole function
    }

    //nish *is* visible out here
}
```

### Redeclaration:

Assuming strict mode, `var` will let you re-declare the same variable in the same scope. On the other hand, `let` will not:

```javascript
'use strict';
let me = 'foo';
let me = 'bar'; // SyntaxError: Identifier 'me' has already been declared
'use strict';
var me = 'foo';
var me = 'bar'; // No problem, `me` is replaced.
```

[Back to Question](#1.1.4)

-------

### 1.2 Scope

<a name='a1.2.1'/>

#### 1.2.1

The above code will output the following to the console:

```javascript
outer func:  this.foo = bar
outer func:  self.foo = bar
inner func:  this.foo = undefined
inner func:  self.foo = bar
```

In the outer function, both `this` and `self` refer to `myObject` and therefore both can properly reference and access `foo`.

In the inner function, though, `this` no longer refers to `myObject`. As a result, `this.foo` is undefined in the inner function, whereas the reference to the local variable `self` remains in scope and is accessible there.

[Back to Question](#1.2.1)

---------

<a name='a1.2.2'/>

#### 1.2.2

This is an increasingly common practice, employed by many popular JavaScript libraries (jQuery, Node.js, etc.). This technique creates a closure around the entire contents of the file which, perhaps most importantly, creates a private namespace and thereby helps avoid potential name clashes between different JavaScript modules and libraries.

Another feature of this technique is to allow for an easily referenceable (presumably shorter) alias for a global variable. This is often used, for example, in jQuery plugins. jQuery allows you to disable the `$` reference to the jQuery namespace, using `jQuery.noConflict()`. If this has been done, your code can still use `$` employing this closure technique, as follows:

```javascript
(function($) { /* jQuery plugin code referencing $ */ } )(jQuery);
```

[Back to Question](#1.2.2)

--------

<a name='a1.2.3'/>

#### 1.2.3

(a) No matter what button the user clicks the number 5 will *always* be logged to the console. This is because, at the point that the `onclick` method is invoked (for *any* of the buttons), the `for` loop has already completed and the variable `i` already has a value of 5. (Bonus points for the interviewee if they know enough to talk about how execution contexts, variable objects, activation objects, and the internal “scope” property contribute to the [closure](#http://conceptf1.blogspot.kr/2013/11/javascript-closures.html) behavior.) 

(b) The key to making this work is to capture the value of `i` at each pass through the `for` loop by passing it into a newly created function object. Here are three possible ways to accomplish this:

```javascript
for (var i = 0; i < 5; i++) {
  var btn = document.createElement('button');
  btn.appendChild(document.createTextNode('Button ' + i));
  btn.addEventListener('click', (function(i) {
    return function() { console.log(i); };
  })(i));
  document.body.appendChild(btn);
}
```

Alternatively, you could wrap the entire call to `btn.addEventListener` in the new anonymous function:

```javascript
for (var i = 0; i < 5; i++) {
  var btn = document.createElement('button');
  btn.appendChild(document.createTextNode('Button ' + i));
  (function (i) {
    btn.addEventListener('click', function() { console.log(i); });
  })(i);
  document.body.appendChild(btn);
}
```

Or, we could replace the `for` loop with a call to the array object’s native `forEach` method:

```javascript
['a', 'b', 'c', 'd', 'e'].forEach(function (value, i) {
  var btn = document.createElement('button');
  btn.appendChild(document.createTextNode('Button ' + i));
  btn.addEventListener('click', function() { console.log(i); });
  document.body.appendChild(btn);
});
```

[Back to Question](#1.2.3)

------

<a name='a1.2.4'/>

#### 1.2.4

A closure is an inner function that has access to the variables in the outer (enclosing) function’s scope chain. The closure has access to variables in three scopes; specifically: (1) variable in its own scope, (2) variables in the enclosing function’s scope, and (3) global variables.

Here is a simple example:

```javascript
var globalVar = "xyz";

(function outerFunc(outerArg) {
  var outerVar = 'a';
  
  (function innerFunc(innerArg) {
    var innerVar = 'b';
    
    console.log(
      "outerArg = " + outerArg + "\n" +
      "innerArg = " + innerArg + "\n" +
      "outerVar = " + outerVar + "\n" +
      "innerVar = " + innerVar + "\n" +
      "globalVar = " + globalVar);
    
  })(456);
})(123);
```

In the above example, variables from `innerFunc`, `outerFunc`, and the global namespace are **all** in scope in the `innerFunc`. The above code will therefore produce the following output:

```javascript
outerArg = 123
innerArg = 456
outerVar = a
innerVar = b
globalVar = xyz
```

[Back to Question](#1.2.4)

--------

<a name='a1.2.5'/>

#### 1.2.5

The code sample shown will **not** display the values 0, 1, 2, 3, and 4 as might be expected; rather, it will display 5, 5, 5, 5, and 5.

The reason for this is that each function executed within the loop will be executed *after* the entire loop has completed and *all* will therefore reference the *last* value stored in `i`, which was 5.

[**Closures**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures) can be used to prevent this problem by creating a unique scope for each iteration, storing each unique value of the variable within its scope, as follows:

```javascript
for (var i = 0; i < 5; i++) {
	(function(x) {
    	setTimeout(function() { console.log(x); }, x * 1000 );
    })(i);
}
```

This will produce the presumably desired result of logging 0, 1, 2, 3, and 4 to the console.

[Back to Question](#1.2.5)

-----

<a name='a1.2.6'/>

#### 1.2.6

The output will be `1`, even though the value of `x` is never set in the inner function. Here’s why:

As explained in our [JavaScript Hiring Guide](https://www.toptal.com/javascript#hiring-guide), a **closure** is a function, along with all variables or functions that were in-scope at the time that the closure was created. In JavaScript, a closure is implemented as an “inner function”; i.e., a function defined within the body of another function. An important feature of closures is that an inner function still has access to the outer function’s variables.

Therefore, in this example, since `x` is not defined in the inner function, the scope of the outer function is searched for a defined variable `x`, which is found to have a value of `1`.

[Back to Question](#1.2.6)

--------

<a name='a1.2.7'/>

#### 1.2.7

The code will output:

```javascript
undefined
John Doe
```

The first `console.log` prints `undefined` because we are extracting the method from the `hero` object, so `stoleSecretIdentity()` is being invoked in the global context (i.e., the window object) where the `_name` property does not exist.

One way to fix the `stoleSecretIdentity()` function is as follows:

```javascript
var stoleSecretIdentity = hero.getSecretIdentity.bind(hero);
```

[Back to Question](#1.2.7)

----------

### 1.3 Error Handling

<a name='a1.3.1'/>

#### 1.3.1

the short and most important answer here is that `use strict` is a way to voluntarily enforce stricter parsing and error handling on your JavaScript code at runtime. Code errors that would otherwise have been ignored or would have failed silently will now generate errors or throw exceptions. In general, it is a good practice.

Some of the key benefits of strict mode include:

- **Makes debugging easier.** Code errors that would otherwise have been ignored or would have failed silently will now generate errors or throw exceptions, alerting you sooner to problems in your code and directing you more quickly to their source.
- **Prevents accidental globals.** Without strict mode, assigning a value to an undeclared variable automatically creates a global variable with that name. This is one of the most common errors in JavaScript. In strict mode, attempting to do so throws an error.
- **Eliminates this coercion**. Without strict mode, a reference to a `this` value of null or undefined is automatically coerced to the global. This can cause many headfakes and pull-out-your-hair kind of bugs. In strict mode, referencing a a `this` value of null or undefined throws an error.
- **Disallows duplicate property names or parameter values.** Strict mode throws an error when it detects a duplicate named property in an object (e.g., `var object = {foo: "bar", foo: "baz"};`) or a duplicate named argument for a function (e.g., `function foo(val1, val2, val1){}`), thereby catching what is almost certainly a bug in your code that you might otherwise have wasted lots of time tracking down.
- **Makes eval() safer.** There are some differences in the way `eval()` behaves in strict mode and in non-strict mode. Most significantly, in strict mode, variables and functions declared inside of an `eval()` statement are *not* created in the containing scope (they *are* created in the containing scope in non-strict mode, which can also be a common source of problems).
- **Throws error on invalid usage of delete.** The `delete` operator (used to remove properties from objects) cannot be used on non-configurable properties of the object. Non-strict code will fail silently when an attempt is made to delete a non-configurable property, whereas strict mode will throw an error in such a case.

[Back to Question](#1.3.1)

------

<a name='a1.3.2'/>

#### 1.3.2

Surprisingly, these two functions will *not* return the same thing. Rather:

```javascript
console.log("foo1 returns:");
console.log(foo1());
console.log("foo2 returns:");
console.log(foo2());
```

will yield:

```javascript
foo1 returns:
Object {bar: "hello"}
foo2 returns:
undefined 
```

Not only is this surprising, but what makes this particularly gnarly is that `foo2()` returns undefined without any error being thrown.

The reason for this has to do with the fact that semicolons are technically optional in JavaScript (although omitting them is generally really bad form). As a result, when the line containing the `return` statement (with nothing else on the line) is encountered in `foo2()`, a semicolon is automatically inserted immediately after the return statement.

No error is thrown since the remainder of the code is perfectly valid, even though it doesn’t ever get invoked or do anything (it is simply an unused code block that defines a property `bar` which is equal to the string `"hello"`).

This behavior also argues for following the convention of placing an opening curly brace at the end of a line in JavaScript, rather than on the beginning of a new line. As shown here, this becomes more than just a stylistic preference in JavaScript.

[Back to Question](#1.3.2)

------

<a name='a1.3.3'/>

#### 1.3.3

The potential stack overflow can be avoided by modifying the `nextListItem` function as follows:

```javascript
var list = readHugeList();

var nextListItem = function() {
    var item = list.pop();

    if (item) {
        // process the list item...
        setTimeout( nextListItem, 0);
    }
};
```

The stack overflow is eliminated because the event loop handles the recursion, not the call stack. When `nextListItem` runs, if `item` is not null, the timeout function (`nextListItem`) is pushed to the event queue and the function exits, thereby leaving the call stack clear. When the event queue runs its timed-out event, the next `item` is processed and a timer is set to again invoke `nextListItem`. Accordingly, the method is processed from start to finish without a direct recursive call, so the call stack remains clear, regardless of the number of iterations.

[Back to Question](#1.3.3)

-----

### 1.4 Numbers

<a name='a1.4.1'/>

#### 1.4.1

An educated answer to this question would simply be: “You can’t be sure. it might print out “0.3” and “true”, or it might not. Numbers in JavaScript are all treated with floating point precision, and as such, may not always yield the expected results.”

The example provided above is classic case that demonstrates this issue. Surprisingly, it will print out:

```javascript
0.30000000000000004
false
```

[Back to Question](#1.4.1)

-------

<a name='a1.4.2'/>

#### 1.4.2

This may sound trivial and, in fact, it is trivial with ECMAscript 6 which introduces a new `Number.isInteger()` function for precisely this purpose. However, prior to ECMAScript 6, this is a bit more complicated, since no equivalent of the `Number.isInteger()` method is provided.

The issue is that, in the ECMAScript specification, integers only exist conceptually; i.e., numeric values are *always* stored as floating point values.

With that in mind, the *simplest and cleanest* pre-ECMAScript-6 solution (which is also sufficiently robust to return `false` even if a non-numeric value such as a string or `null` is passed to the function) would be the following:

```javascript
function isInteger(x) { return (x^0) === x; } 
```

The following solution would also work, although not as elegant as the one above:

```javascript
function isInteger(x) { return Math.round(x) === x; }
```

Note that `Math.ceil()` or `Math.floor()` could be used equally well (instead of `Math.round()`) in the above implementation.

Or alternatively:

```javascript
function isInteger(x) { return (typeof x === 'number') && (x % 1 === 0); }
```

One fairly common **incorrect** solution is the following:

```javascript
function isInteger(x) { return parseInt(x, 10) === x; }
```

While this `parseInt`-based approach will work well for *many* values of `x`, once `x` becomes quite large, it will fail to work properly. The problem is that `parseInt()` coerces its first parameter to a string before parsing digits. Therefore, once the number becomes sufficiently large, its string representation will be presented in exponential form (e.g., `1e+21`). Accordingly, `parseInt()` will then try to parse `1e+21`, but will stop parsing when it reaches the `e` character and will therefore return a value of `1`. Observe:

```javascript
> String(1000000000000000000000)
'1e+21'

> parseInt(1000000000000000000000, 10)
1

> parseInt(1000000000000000000000, 10) === 1000000000000000000000
false
```

[Back to Question](#1.4.2)

------

### 1.5 Events and Runtime

<a name='a1.5.1'/>

#### 1.5.1

The values will be logged in the following order:

```javascript
1
4
3
2
```

Let’s first explain the parts of this that are presumably more obvious:

- `1` and `4` are displayed first since they are logged by simple calls to `console.log()` without any delay
- `2` is displayed after `3` because `2` is being logged after a delay of 1000 msecs (i.e., 1 second) whereas `3` is being logged after a delay of 0 msecs.

OK, fine. But if `3` is being logged after a delay of 0 msecs, doesn’t that mean that it is being logged right away? And, if so, shouldn’t it be logged *before* `4`, since `4` is being logged by a later line of code?

The answer has to do with properly understanding [JavaScript events and timing](http://javascript.info/tutorial/events-and-timing-depth).

The browser has an event loop which checks the event queue and processes pending events. For example, if an event happens in the background (e.g., a script `onload` event) while the browser is busy (e.g., processing an `onclick`), the event gets appended to the queue. When the onclick handler is complete, the queue is checked and the event is then handled (e.g., the `onload` script is executed).

Similarly, `setTimeout()` also puts execution of its referenced function into the event queue if the browser is busy.

When a value of zero is passed as the second argument to `setTimeout()`, it attempts to execute the specified function “as soon as possible”. Specifically, execution of the function is placed on the event queue to occur on the next timer tick. Note, though, that this is *not* immediate; the function is not executed until the next tick. That’s why in the above example, the call to `console.log(4)` occurs before the call to `console.log(3)` (since the call to `console.log(3)` is invoked via setTimeout, so it is slightly delayed).

[Back to Question](#1.5.1)

------

### 1.6 Functions

<a name='a1.6.1'/>

#### 1.6.1

There are (at least) two ways to do this:

**METHOD 1**

```javascript
function sum(x) {
  if (arguments.length == 2) {
    return arguments[0] + arguments[1];
  } else {
    return function(y) { return x + y; };
  }
}
```

In JavaScript, functions provide access to an `arguments` object which provides access to the actual arguments passed to a function. This enables us to use the `length` property to determine at runtime the number of arguments passed to the function.

If two arguments are passed, we simply add them together and return.

Otherwise, we assume it was called in the form `sum(2)(3)`, so we return an anonymous function that adds together the argument passed to `sum()` (in this case 2) and the argument passed to the anonymous function (in this case 3).

**METHOD 2**

```javascript
function sum(x, y) {
  if (y !== undefined) {
    return x + y;
  } else {
    return function(y) { return x + y; };
  }
}
```

When a function is invoked, JavaScript does not require the number of arguments to match the number of arguments in the function definition. If the number of arguments passed exceeds the number of arguments in the function definition, the excess arguments will simply be ignored. On the other hand, if the number of arguments passed is less than the number of arguments in the function definition, the missing arguments will have a value of `undefined` when referenced within the function. So, in the above example, by simply checking if the 2nd argument is undefined, we can determine which way the function was invoked and proceed accordingly.

[Back to Question](#1.6.1)

---------

<a name='a1.6.2'/>

#### 1.6.2

The code will output the value of 10 factorial (i.e., 10!, or 3,628,800).

Here’s why:

The named function `f()` calls itself recursively, until it gets down to calling `f(1)` which simply returns `1`. Here, therefore, is what this does:

```javascript
f(1): returns n, which is 1
f(2): returns 2 * f(1), which is 2
f(3): returns 3 * f(2), which is 6
f(4): returns 4 * f(3), which is 24
f(5): returns 5 * f(4), which is 120
f(6): returns 6 * f(5), which is 720
f(7): returns 7 * f(6), which is 5040
f(8): returns 8 * f(7), which is 40320
f(9): returns 9 * f(8), which is 362880
f(10): returns 10 * f(9), which is 3628800
```

[Back to Question](#1.6.2)

-----

### 1.7 Reference

<a name='a1.7.1'/>

#### 1.7.1

The logged output will be:

```javascript
"array 1: length=5 last=j,o,n,e,s"
"array 2: length=5 last=j,o,n,e,s"
```

`arr1` and `arr2` are the same after the above code is executed for the following reasons:

- Calling an array object’s `reverse()` method doesn’t only *return* the array in reverse order, it also reverses the order of the array *itself* (i.e., in this case, `arr1`).
- The `reverse()` method returns a reference to the array itself (i.e., in this case, `arr1`). As a result, `arr2` is simply a reference to (rather than a copy of) `arr1`. Therefore, when anything is done to `arr2` (i.e., when we invoke `arr2.push(arr3);`), `arr1` will be affected as well since `arr1` and `arr2` are simply references to the same object.

And a couple of side points here that can sometimes trip someone up in answering this question:

- Passing an array to the `push()` method of another array pushes that *entire* array as a *single* element onto the end of the array. As a result, the statement `arr2.push(arr3);` adds `arr3` in its entirety as a single element to the end of `arr2` (i.e., it does *not* concatenate the two arrays, that’s what the `concat()` method is for).
- Like Python, JavaScript honors negative subscripts in calls to array methods like `slice()` as a way of referencing elements at the end of the array; e.g., a subscript of -1 indicates the last element in the array, and so on.

[Back to Question](#1.7.1)

-----

### 1.8 Comparison and Logical Operators

<a name='a1.8.1'/>

#### 1.8.1

The code will output the following four lines:

```javascript
0 || 1 = 1
1 || 2 = 1
0 && 1 = 0
1 && 2 = 2
```

In JavaScript, both `||` and `&&` are logical operators that return the first fully-determined “logical value” when evaluated from left to right.

**The or (||) operator.** In an expression of the form `X||Y`, `X` is first evaluated and interpreted as a boolean value. If this boolean value is `true`, then `true` (1) is returned and `Y` is not evaluated, since the “or” condition has already been satisfied. If this boolean value is “false”, though, we still don’t know if `X||Y` is true or false until we evaluate `Y`, and interpret it as a boolean value as well.

Accordingly, `0 || 1` evaluates to true (1), as does `1 || 2`.

**The and (&&) operator.** In an expression of the form `X&&Y`, `X` is first evaluated and interpreted as a boolean value. If this boolean value is `false`, then `false` (0) is returned and `Y` is not evaluated, since the “and” condition has already failed. If this boolean value is “true”, though, we still don’t know if `X&&Y` is true or false until we evaluate `Y`, and interpret it as a boolean value as well.

However, the interesting thing with the `&&` operator is that when an expression is evaluated as “true”, then the expression itself is returned. This is fine, since it counts as “true” in logical expressions, but also can be used to return that value when you care to do so. This explains why, somewhat surprisingly, `1 && 2` returns 2 (whereas you might it expect it to return `true` or `1`).

[Back to Question](#1.8.1)

------

<a name='a1.8.2'/>

#### 1.8.2

The code will output:

```javascript
true
false
```

In JavaScript, there are two sets of equality operators. The triple-equal operator `===` behaves like any traditional equality operator would: evaluates to true if the two expressions on either of its sides have the same type and the same value. The double-equal operator, however, tries to coerce the values before comparing them. It is therefore generally good practice to use the `===` rather than `==`. The same holds true for `!==` vs `!=`.

[Back to Question](#1.8.2)

---------

### 1.9 Objects

<a name='a1.9.1'/>

#### 1.9.1

The output of this code will be `456` (*not* `123`).

The reason for this is as follows: When setting an object property, JavaScript will implicitly **stringify** the parameter value. In this case, since `b` and `c` are both objects, they will *both* be converted to `"[object Object]"`. As a result, `a[b]` and`a[c]` are both equivalent to `a["[object Object]"]` and can be used interchangeably. Therefore, setting or referencing `a[c]` is precisely the same as setting or referencing `a[b]`.

[Back to Question](#1.9.1)

-----

<a name='a1.9.2'/>

#### 1.9.2

This is somewhat of a trick question since, in JavaScript, objects essentially are hashtables; i.e., collections of name-value pairs. In these name-value pairs, a crucial point to be aware of is that the names (a.k.a., keys) are always strings.

[Back to Question](#1.9.2)

--------

### 1.10 DOM (Document Object Model)

<a name='a1.10.1'/>

#### 1.10.1

Visiting all elements in a tree (DOM) is a classic [Depth-First-Search algorithm](https://en.wikipedia.org/wiki/Depth-first_search) application. Here’s an example solution:

```javascript
function Traverse(p_element,p_callback) {
   p_callback(p_element);
   var list = p_element.children;
   for (var i = 0; i < list.length; i++) {
       Traverse(list[i],p_callback);  // recursive call
   }
}
```

[Back to Question](#1.10.1)

-------

### 1.11 Prototype

<a name='a1.11.1'/>

#### 1.11

Although JavaScript is an object-oriented language, it is prototype-based and does not implement a traditional class-based inheritance system.

In JavaScript, each object internally references another object, called its *prototype*. That prototype object, in turn, has a reference to its prototype object, and so on. At the end of this prototype chain is an object with null as its prototype. The prototype chain is the mechanism by which inheritance – *prototypal inheritance* to be precise – is achieved in JavaScript. In particular, when a reference is made to a property that an object does not itself contain, the prototype chain is traversed until the referenced property is found (or until the end of the chain is reached, in which case the property is undefined).

Here’s a simple example:

```javascript
function Animal() { this.eatsVeggies = true; this.eatsMeat = false; }

function Herbivore() {}
Herbivore.prototype = new Animal();

function Carnivore() { this.eatsMeat = true; }
Carnivore.prototype = new Animal();

var rabbit = new Herbivore();
var bear = new Carnivore();

console.log(rabbit.eatsMeat);   // logs "false"
console.log(bear.eatsMeat);     // logs "true"
```

[Back to Question](#1.11.1)

---------

<a name='a2.1'/>

### 2.1 String Palindrome

The following one line function will return `true` if `str` is a palindrome; otherwise, it returns false.

```javascript
function isPalindrome(str) {
    str = str.replace(/\W/g, '').toLowerCase(); //removes all non-word character
    return (str == str.split('').reverse().join('')); //remove space, reverse, and check
}
```

For example:

```javascript
console.log(isPalindrome("level"));                   // logs 'true'
console.log(isPalindrome("levels"));                  // logs 'false'
console.log(isPalindrome("A car, a man, a maraca"));  // logs 'true'
```

[Back to Question](#2.1)

------

<a name='a2.2'/>

### 2.2 Square Root

```javascript
//@param number number to find the square root of
//@param guess number of guesses
function sqrt(number, guess) {
    if (!guess) {
        // Take an initial guess at the square root
        guess = number / 2.0;
    }
    var d = number / guess;              // Divide our guess into the number
    var new_guess = (d + guess) / 2.0;     // Use average of guess and d as our new guess
    if (guess == new_guess) {          
        // The new guess is the same as the old guess; further guesses
        // can get no more accurate so we return this guess
        return guess;
    }
    // Recursively solve for closer and closer approximations of the square root
    return sqrt(number, new_guess);
}
```

[Back to Question](#2.2)

-----------

<a name='a2.3'/>

### 2.3 Flattening Arrays

```javascript
function flatten(input) {
    let out = [];
    let loop = function(arr) {
        return arr.map(function(v) {
            return Array.isArray(v)? loop(v) : out.push(v);
        });
    }
    loop(input);
    return out;
}
```

[Back to Question](#2.3)

----

<a name='a2.4'/>

### 2.4 Reordering Objects in an Array

```javascript
function sort(A, B) {
	let result = [];
	B.map((index, i) => {
		result[index] = A[i];
	})
	return result;
}
```

[Back to Question](#2.4)

------

<a name='a2.5'/>

### 2.5 Replacing Substring

```javascript
var string = "ABCSC"; 

return ((string.indexOf("ABC") != -1) ? (string.replace(/ABC/gm,"")) : (-1));
```

[Back to Question](#2.5)

-----

<a name='a2.6'/>

### 2.6 Move Zeroes

```javascript
/**
 * @param {number[]} nums
 * @return {void} Do not return anything, modify nums in-place instead.
 */
var moveZeroes = function(nums) {
    let j = 0;
    nums.map((num, i) => {
        if(num !== 0) { //if number is not 0
          	//swap the num[i] and num[j]
            let temp = nums[j];
            nums[j] = nums[i];
            nums[i] = temp;
            j++;
        }
    })
};
```

[Back to Question](#2.6)

--------

## Credits

- [Toptal](#https://www.toptal.com/javascript/interview-questions)
- [Difference between `let` and `var`](#http://stackoverflow.com/questions/762011/whats-the-difference-between-using-let-and-var-to-declare-a-variable)
