# Single Page Applications with Vue

**1.** What is the entrypoint of an application?
<!-- enter you answer in the space below -->
```
main.js
```
**2.** What is the difference between a vue `component` and `page`?
<!-- enter you answer in the space below -->
```
a component is just a bit of code linked into a page while a page is what's actually rendered in the browser
```
**3.** What feature of Vue can be used to repeat an element using a collection of data?
<!-- enter you answer in the space below -->
```
v-for="item in list" :key="<key for unique value>"
```
**4.** What are the three tags that make up a Vue component?
<!-- enter you answer in the space below -->
```
<template></template> <script></script> <style></style>??
```
**5.** What does the `L` represent in the `SOLID` principles?
<!-- enter you answer in the space below -->
```
Functions that use pointers or references to base classes must be able to use objects of derived classes without knowing it.

This has to do with extending classes. Objects from child classes can use properties from the parent class without referencing that parent class
```
**6.** Which component in Vue does the vue-router use to mount pages onto?
<!-- enter you answer in the space below -->
```
app.vue <router-view />
```
**7.** What is the difference between the `AppState` and the state object within a component?
<!-- enter you answer in the space below -->
```
The state component has variables that are scoped to that component while the appstate has variables accessible across the application
```
**9.** What is the responsibility of `Services` in our Vue projects?
<!-- enter you answer in the space below -->
```
To get/post/put/delete and otherwise change the data
```
**10.** Which file contains the root element of your Vue project?
<!-- enter you answer in the space below -->
```
index.html??
```
**11.** The ______ tag is used to alter the styling of your entire Vue project.  Adding the ______ attribute to this tag will limit it to just the component it exists.  Fill in the blank.
<!-- enter you answer in the space below -->
```
style/ scoped
```
**12.** What is the Vue method used to create watchable objects such as `state` or `AppState`?
<!-- enter you answer in the space below -->
```
reactive() computed() ref()??
```