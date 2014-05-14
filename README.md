# Node.js Style Guide

This style guide is a list of dos and don'ts for JavaScript programs for writing consistent and aesthetically pleasing node.js code. It is inspired by what is popular within the community, and flavored with some personal opinions.

## JavaScript Files

JavaScript programs should be stored in and delivered as .js files.

## Indentation

Use 2 spaces for indenting your code and swear an oath to never mix tabs and
spaces - a special kind of hell is awaiting you otherwise. 

Use of tabs should be avoided because (as of this writing in the 21st Century) there still is not a standard for the placement of tabstops. The use of spaces can produce a larger filesize.

## Trailing whitespace

Just like you brush your teeth after every meal, you clean up any trailing
whitespace in your JS files before committing. Otherwise the rotten smell of
careless neglect will eventually drive away contributors and/or co-workers.

## Line Length

Limit your lines to 80 characters. Yes, screens have gotten much bigger over the
last few years, but your brain has not. Use the additional room for split screen,
your editor supports that, right?

Place the break after an operator, ideally after a comma. A break after an operator decreases the likelihood that a copy-paste error will be masked by semicolon insertion. The next line should be indented 8 spaces.

## Comments

Use JSDoc

## Variable Declarations

All variables should be declared before used. JavaScript does not require this, but doing so makes the program easier to read and makes it easier to detect undeclared variables that may become implied globals. Implied global variables should never be used.

Declare one variable and its comment per var statement, it makes it easier to re-order the lines.
lines.

Example:

    var currentEntry; // currently selected table entry
    var level;        // indentation level
    var size;         // size of table

When it comes to declaring variables deeper inside a function, just the declarations wherever they make sense.

## Function Declarations