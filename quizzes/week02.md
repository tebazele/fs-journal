# Intro to JavaScript

**1.** Which keywords are used to declare a variable in JavaScript?
<!-- enter you answer in the space below -->
```
var let const
```
**2.** What is the definition of a function?
<!-- enter you answer in the space below -->
```
Subprogram designed to perform a specific task
```
**3.** What are the `SOLID` principles?
<!-- enter you answer in the space below -->
```
S: Single-responsibility (each part of your code should do one thing)
O: Open-close (the code should be open to additions, but each bit of functionality should be closed/self-contained OR you shouldn't have to rewrite your code to add features)
L: Liskov substitution (Once the user has learned what your code does, any changes in the code should still work the same for the user??)
I: Interface-segregation (code written for a specific purpose/specific user that doesn't try to do everything is better than general-purpose code (this is why gen-purpose site creators like SquareSpace are always subpar))
D: Dependency-inversion (use abstraction to help handle corner-cases and changes)
```
**4.** Given this array: 
```js
let fruit = ['apple', 'banana', 'pineapple',  'orange', 'strawberry']
``` 
What index is the pineapple's current position? How do you know?
<!-- enter you answer in the space below -->
```
2, you start counting from the 0 index
```
**5.** With these two objects: 
```js
let you = { name:"You", hair: true, friends: [] }
let them = { name:"Them", hair: false, friends: [] }
```
how would you .push the `them` object into the `you` object's array of friends?
<!-- enter you answer in the space below -->
```
you.friends.push("them")
```

**6.** Give an example of a JavaScript `Conditional`:
<!-- enter you answer in the space below -->
```
if (num > 10) {
  console.log('greater than 10')
} else {
  console.log('less than 10')
}
```
**7.** In the `for loop` below, what is the name of the piece belongs inside the empty "______" space? What would you put here to increase `i` by one on every iteration?
```js
for ( let i = 0; i < arr.length; _______ ) {
  //...
```
<!-- enter you answer in the space below -->
```
iterator; i++
```
**8.** What does the `DOM` acronym stand for? Which file is first accessed to render the `DOM`?
<!-- enter you answer in the space below -->
```
document object model; document
```

**9.** What are the `9` ECMAScript types as defined by MDN?
<!-- enter you answer in the space below -->
```
string, number, boolean, undefined, null, array, object, BigInt?, Symbol?, Date?, Map?
```
**10.** When it comes to functions or methods, what is the difference between a `parameter` and an `argument`?
<!-- enter you answer in the space below -->
```
A parameter is the banana word you write in the parens of the function definition and use as a stand-in in the function body for whatever you plan to put in there (the argument) when you invoke the function later.
```
**11.** What is the difference between a `primitive` value and a `reference` value?
<!-- enter you answer in the space below -->
```
primitive values are simple values like a number or a string while reference values hold more complicated data
```