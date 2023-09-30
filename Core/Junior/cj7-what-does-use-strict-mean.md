### What does use strict mean?
**"use strict"** is a directive which you can write on top of script or function to ensure that only "modern" JS will be valid, and using the obsolete tactics, principle will cause errors. Modules and classes are automatically "use strict" so there is no no need to write it there. Is was released along with ES5, where a lot of old fuctions and principles where marked as obsolete. However if ypu do not use "use strict" there is no need to rewrite the old code, all new ES releases support old versions. 
**Examples of what is no supported by use strict mode**
1. Using a variable before initialisation. In non-strict mode (the default), if you forget to declare a variable with var, let, or const, it becomes a global variable. In strict mode, this behavior is disallowed, and forgetting to declare a variable will result in a reference error.
```
console.log(a);
var a = 5; //error: can't use variable before initialization.
```
2. Deleting object or functions. You cannot use the delete operator to delete variables or functions declared with var, let, or const.
```
let a = {num:1, name:'Maya'};
delete a; //error
```
3. Initializing of undeclared variables. In strict mode, attempting to assign a value to a read-only global object (e.g., undefined, NaN, or Infinity) will result in an error.
```
x = 1,14; //error: can't initialize undeclared x variable.
```
4. Duplicated arguments in the functions.
```
function multiply(x,x) {}; //error: duplicated arguments.
```
5. Octal values are forbidden.
```
x=010; //error: octal value.
```

>Octal values are numbers with leading zero. What is a problem with that? It can lead to a lot of errors. For example.
```
let x = 1;
let y1 = 10;
let newVar = 10;
```
> I do not like how it looks, so I an trying to aline it with leading zeroes (knowing that they will be automatically removed).
```
let x = 0000001;
let y1 = 000010;
let newVar = 10;
```
> What will I receive (x: 1, y1: 8, newVar: 10), not what I have expected right. It happened because leading zero means that base is 8, not 10.