Node.js Style Guide
===================

This style guide is a list of dos and don'ts for JavaScript programs for writing consistent and aesthetically pleasing node.js code. It is inspired by what is popular within the community, and flavored with some personal opinions.

JavaScript Language Rules
-------------------------

### Variables

Declarations with var: Always 

When you fail to specify var, the variable gets placed in the global context, potentially clobbering existing values. Also, if there's no declaration, it's hard to tell in what scope a variable lives (e.g., it could be in the Document or Window just as easily as in the local scope). So always declare with var. 

### Constants

### Semicolons

### Nested functions

### Function Declarations Within Blocks

### Exceptions

### Custom exceptions

### Standards features

### Wrapper objects for primitive types

### Multi-level prototype hierarchies

### Method and property definitions

### Delete property

### Closures

### eval

### with

### this

### for-in loop

### Associative Arrays

### Multiline string literals

### Array and Object literals

### Modifying prototypes of builtin objects

### Internet Explorer's Conditional Comments

JavaScript Style Rules
----------------------

### Naming

### Custom toString() methods

### Deferred initialization

### Explicit scope

### Code formatting

### Parentheses

### Strings

### Visibility (private and protected fields)

### JavaScript Types

### Comments

### Compiling

### Tips and Tricks

