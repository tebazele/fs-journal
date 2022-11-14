# Application Architecture, MVC Design Pattern

**1.** What are the Pillars of Object Oriented Programming (`OOP`)?
<!-- enter you answer in the space below -->
```
encapsulation, inheritance, polymorphism 
```
**2.** How would you access the `name` of the below object using the `property` variable?
```js
let staff = {
  name: "Tim",
  age: 26,
  job: "Code Monkey"
  }
let property = 'name'
```
<!-- enter you answer in the space below -->
```
staff.property
```
**3.** What is Encapsulation?
<!-- enter you answer in the space below -->
```
encapsulation is wrapping up bits of code so not everything is accessible to every part of the application and subsequently the user. Code is accessible as an object with certain (developer-defined) properties and methods
```
**4.** What does the S stand for in the `SOLID` principles?
<!-- enter you answer in the space below -->
```
single-responsibility
```
**5.** What the difference between a `class` and an instance of a `class`?
<!-- enter you answer in the space below -->
```
A class is like an object factory or a recipe. It just tells you how to create an object with those properties and methods. An instance of a class is an object with specific (developer-defined) properties and methods.
```
**6.** What is a `Proxy` object?
<!-- enter you answer in the space below -->
```
an instance of the Proxy class that sets up certain 'traps' that trip when a user tries to access or reassign properties on an original object/target. I'm not sure I totally get this one yet.
```

**7.** What is the purpose of the `MVC` pattern?
<!-- enter you answer in the space below -->
```
To prevent the user from accessing private functions, methods, and properties and to make the code simpler and separate the parts into defined sections. 
```
**8.** What is the job of the `Controller` in the `MVC` Pattern?
<!-- enter you answer in the space below -->
```
The controller takes in events from the view and draws to the view
```

**9.** What is the job of the `Service` in `MVC`?
<!-- enter you answer in the space below -->
```
The service manipulates the data in the appState
```
**10.** What is the job of the `Model` in `MVC`?
<!-- enter you answer in the space below -->
```
The model is like the blueprint from which data is created.
```
