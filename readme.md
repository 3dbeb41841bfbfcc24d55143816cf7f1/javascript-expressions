# JavaScript Expressions and Data Types

## JavaScript History and Fun Facts

* JavaScript is not to be confused with Java, they are 2 completely different programming languages.
* JavaScript was created in 10 days in May 1995 by Brendan Eich, then working at Netscape and now of Mozilla.
* Eich was inspired by several other languages including ***Scheme*** (a variant of Lisp) and ***Self***.
* In 1996 - 1997 JavaScript was taken to ECMA to carve out a standard specification, which other browser vendors could then implement based on the work done at Netscape.
* JavaScript has become the de facto standard language for Web pages running in a browser.
* Thanks to NodeJS and the V8 JavaScript engine developed at Google, JavaScript can now be used outside of the browser as a general purpose, full featured programming language.
* JavaScript is arguably the fastest growing (in popularity) programming language.
* JavaScript is a general purpose programming language that supports the two most common programming paradigms: ***Object Oriented Programming*** (OOP) and ***Functional Programming*** (FP).
* JavaScript is [the world's most misunderstood programming language](http://javascript.crockford.com/javascript.html)

## Javascript and HTML Pages - Where does the JavaScript go?

When placing JavaScript in a web page, the JavaScript can go in one of the following locations:

* In a script tag inside the head section
* In a script tag inside the body section
* In a separate file loaded by the script tag

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Yo</title>
    <script>
      console.log('I am in the head section.');
      var x = 3;
      console.log('The value of x is ' + x);
    </script>
    <script src="script.js"></script>
  </head>
  <body>
    <h1>Hello, WDI!</h1>
    <script>
      console.log('I am in the body section.');
      x += 5;
      console.log('The value of x is ' + x);
    </script>
  </body>
</html>
```



## Variables
* JavaScript variables are declared using the ***var*** keyword.
* JavaScript variables have a ***name*** and a ***value***.
* JavaScript names should be camelCase (a common best practice / rule of thumb).
* Values are of a ***type*** such as ***String***, ***Number***, or ***Boolean***.

Here are some examples of JavaScript Variables:

```javascript
var greeting = 'Hello, WDI!';             // a String
var year = 2015;                          // a Number
var pi = 3.14159;                         // a Number
var completed = false;                    // a Boolean (can be true or false)
var fruit = ['Apple', 'Orange', 'Banana'] // an Array
var person = {                            // an Object
  firstName: 'Mike',
  lastName: 'Hopper'
};
var fullName = person.firstName + ' ' + person.lastName;
```

## Comments
You can add single-line comments to JavaScript using `//` and multi-line comments using `/*` and `*/`.

```javascript

// this is a single line comment.

var x = 3;     // this is a comment at the end of a line.

/* This is a multi-line comment, good for longer comments that need to span
multiple lines.
*/

var y = 4;
```

## Datatypes

* Primary: String, Number, Boolean
* Composite: Array, Object
* Special Values: null, undefined, NaN

### Number Operations

JavaScript's numeric operators are +, -, *, / and %, the latter being the remainder operator (which is not the same as modulo for negative numbers).

```javascript
var x = 3;
var y = 4;
var sum = x + y;                    // 7
var product = x * y;                // 12
```

Operators have a precedence (just like we learned in grade school). The precedence is:

1. parentheses: ()
2. *, /, %
3. +, -

This can be remembered by the mneumonic PeMDAS (Parentheses, Multiplication, Division, Addition, Subtraction).

Expressions are evaluated from higher to lower precedence and then from left to right. For example:

```javascript
var x = 3 + 4 * 5 / 2 - 1;
```

will be evaluated as:

3 + ( (4 * 5) / 2 ) - 1       // multiplication and division first (executed left to right)
3 + ( (20 / 2 ) - 1
3 + 10 - 1                    // addition and subtraction last (executed left to right)
13 - 1
12

Question: what is the output of the following:

```javascript
var x = 5;
var y = 3;
var answer = 2 + x * (x + 1) / y - 3;
console.log(answer);
```

Try it in your browser to confirm your answer.

There are also compound assignment statements such as += and -=. These extend out to x = x operator y.

```javascript
var x = 3;
var y = 4;
x += 10;                            // 13  (equivalent to x = x + 10)
y *= 2;                             // 8   (equivalent to y = y * 2)
```

### Strings and String Operations

* String literals can be written with single quotes or double quotes:

```javascript
var city = 'Atlanta';
var state = "Georgia";
```

* Strings have a set of properties and methods that can be used to get information about the string, get parts of the string, or manipulate the string in some way:

```javascript
var greeting = 'Hello, WDI!';
greeting.length;                    // 11
greeting.charAt(0);                 // 'H'
greeting.charAt(5);                 // ','
greeting.indexOf('W');              // 7
greeting.substring(7, 10);          // 'WDI'
greeting.toLowerCase();             // 'hello, wdi!'
greeting.toUpperCase();             // 'HELLO, WDI!'
greeting;                           // 'Hello, WDI!' (has not changed)
```

* Strings can be joined together (concatenated) using the `+` operator:

```javascript
var city = 'Atlanta';
var state = "GA";
var zipcode = '30308';

var address = city + ', ' + state + ' ' + zipcode;  // 'Atlanta, GA 30308'
```

### Converting Strings to Numbers

```javascript
parseInt('25374', 10);              // 25374
parseInt('hello', 10);              // NaN
```

## Booleans
* A boolean value can be either **true** or **false**.
* Boolean values can be combined using the logical operators && (AND) and || (OR).
* The boolean ! (NOT) operator will invert the boolean value.
* The order of boolean operator precedence is:
  1. !
  2. &&
  3. ||


```javascript
var a = 3;
var b = 5;
var c = -12;
var x = a < b;   // true
var y = c > 0;   // false

!x               // false
x && y           // false
x || y           // true
x && !y          // true
```

## Special Values
JavaScript has 2 special values, **null** and **undefined**.

* null - indicates a deliberate non-value
* undefined - indicates an uninitialized value

```javascript
var x = null;                       // the value of x is null
var y;                              // the value of y is undefined
```
