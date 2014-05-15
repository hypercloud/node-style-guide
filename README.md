# Node.js Style Guide

This style guide is a list of dos and don'ts for JavaScript programs for writing consistent and aesthetically pleasing node.js code. It is inspired by what is popular within the community, and flavored with some personal opinions.

## Indentation

Use 2 spaces for indenting your code and swear an oath to never mix tabs and
spaces - a special kind of hell is awaiting you otherwise. 

Use of tabs should be avoided because (as of this writing in the 21st Century) there still is not a standard for the placement of tabstops. The use of spaces can produce a larger filesize.

## Trailing whitespace

Just like you brush your teeth after every meal, you clean up any trailing
whitespace in your JS files before committing. Otherwise the rotten smell of
careless neglect will eventually drive away contributors and/or co-workers.

## Semicolons

According to [scientific research][hnsemicolons], the usage of semicolons is
a core value of our community. Consider the points of [the opposition][], but
be a traditionalist when it comes to abusing error correction mechanisms for
cheap syntactic pleasures.

[the opposition]: http://blog.izs.me/post/2353458699/an-open-letter-to-javascript-leaders-regarding
[hnsemicolons]: http://news.ycombinator.com/item?id=1547647

## Line Length

Limit your lines to 80 characters. Yes, screens have gotten much bigger over the
last few years, but your brain has not. Use the additional room for split screen,
your editor supports that, right?

Place the break after an operator, ideally after a comma. A break after an operator decreases the likelihood that a copy-paste error will be masked by semicolon insertion. The next line should be indented 8 spaces.

## Quotes

Use single quotes, unless you are writing JSON.

*Right:*

```js
var foo = 'bar';
```

*Wrong:*

```js
var foo = "bar";
```

## Braces

Your opening braces go on the same line as the statement.

*Right:*

```js
if (true) {
  console.log('winning');
}
```

*Wrong:*

```js
if (true)
{
  console.log('losing');
}
```

Also, notice the use of whitespace before and after the condition statement.

## Comments

Use JSDoc

## Variable Declarations

All variables should be declared before used. JavaScript does not require this, but doing so makes the program easier to read and makes it easier to detect undeclared variables that may become implied globals. Implied global variables should never be used.

Declare one variable and its comment per var statement, it makes it easier to re-order the lines.
lines.

*Example:*

```js
var currentEntry; // currently selected table entry
var level;        // indentation level
var size;         // size of table
```

When it comes to declaring variables deeper inside a function, just the declarations wherever they make sense.

### Object / Array creation

Use trailing commas and put *short* declarations on a single line. Only quote
keys when your interpreter complains:

*Right:*

```js
var a = ['hello', 'world'];
var b = {
  good: 'code',
  'is generally': 'pretty',
};
```

*Wrong:*

```js
var a = [
  'hello', 'world'
];
var b = {"good": 'code'
        , is generally: 'pretty'
        };
```

## Function Declarations

All functions should be declared before they are used. Inner functions should follow the var statement. This helps make it clear what variables are included in its scope.

There should be no space between the name of a function and the ( (left parenthesis) of its parameter list. There should be one space between the ) (right parenthesis) and the { (left curly brace) that begins the statement body. The body itself is indented two spaces. The } (right curly brace) is aligned with the line containing the beginning of the declaration of the function.

*Example:* 

```js
function outer(c, d) {
  var e = c * d;

  function inner(a, b) {
    return (e * a) + b;
  }

  return inner(0, 1);
}
```

### Function length

Keep your functions short. A good function fits on a slide that the people in
the last row of a big room can comfortably read. So don't count on them having
perfect vision and limit yourself to ~15 lines of code per function.

## Names

Names should be formed from the 26 upper and lower case letters (A .. Z, a .. z), the 10 digits (0 .. 9), and _ (underbar). Avoid use of international characters because they may not read well or be understood everywhere. Do not use $ (dollar sign) or \ (backslash) in names.

Do not use _ (underbar) as the first character of a name. It is sometimes used to indicate privacy, but it does not actually provide privacy. If privacy is important, use the forms that provide private members. Avoid conventions that demonstrate a lack of competence.

Most variables and functions should start with a lower case letter.

### Variable, property and function names

Variables, properties and function names should use `lowerCamelCase`.  They
should also be descriptive. Single character variables and uncommon
abbreviations should generally be avoided.

*Right:*

```js
var adminUser = db.query('SELECT * FROM users ...');
```

*Wrong:*

```js
var admin_user = db.query('SELECT * FROM users ...');
```

### Class names

Class names should be capitalized using `UpperCamelCase`.

*Right:*

```js
function BankAccount() {
}
```

*Wrong:*

```js
function bank_Account() {
}
```

### Constants

Constants should be declared as regular variables or static class properties,
using all uppercase letters.

Node.js / V8 actually supports mozilla's [const][const] extension, but
unfortunately that cannot be applied to class members, nor is it part of any
ECMA standard.

*Right:*

```js
var SECOND = 1 * 1000;

function File() {
}
File.FULL_PERMISSIONS = 0777;
```

*Wrong:*

```js
const SECOND = 1 * 1000;

function File() {
}
File.fullPermissions = 0777;
```

[const]: https://developer.mozilla.org/en/JavaScript/Reference/Statements/const

## Statements

### Simple Statements

Each line should contain at most one statement. Put a ; (semicolon) at the end of every simple statement. Note that an assignment statement which is assigning a function literal or object literal is still an assignment statement and must end with a semicolon.

JavaScript allows any expression to be used as a statement. This can mask some errors, particularly in the presence of semicolon insertion. The only expressions that should be used as statements are assignments and invocations.

### Compound Statements

Compound statements are statements that contain lists of statements enclosed in { } (curly braces).

* The enclosed statements should be indented four more spaces.
* The { (left curly brace) should be at the end of the line that begins the compound statement.
* The } (right curly brace) should begin a line and be indented to align with the beginning of the line containing the matching { (left curly brace).
* Braces should be used around all statements, even single statements, when they are part of a control structure, such as an if or for statement. This makes it easier to add statements without accidentally introducing bugs.

### Equality operator

Programming is not about remembering [stupid rules][comparisonoperators]. Use
the triple equality operator as it will work just as expected.

*Right:*

```js
var a = 0;
if (a !== '') {
  console.log('winning');
}

```

*Wrong:*

```js
var a = 0;
if (a == '') {
  console.log('losing');
}
```

[comparisonoperators]: https://developer.mozilla.org/en/JavaScript/Reference/Operators/Comparison_Operators