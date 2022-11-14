# JavaScript

<!-- SECTION variables -->
<h1>Variables</h1>

let and var are hoisted within their scope

var can be redefined (var greeting="hello"; var greeting="hi";)

let variables can be re-assigned but not redefined

var is initialized as undefined; let is not (if you use let variable before assignment, you get a reference error)

const and let variables are block scoped

const cannot be redefined or reassigned

const must be initialized at declaration

const object values can be changed

<!-- SECTION lecture notes 10/31/22 -->
undefined: unknown nothing
null: known nothing
both are "any" datatype

key and value pairs inside objects have no order;

// clear() -clears console

reference type is a link that gets created between values;

<!-- SECTION lecture notes 11/1/22 -->
notes in PATH: Source/Codeworks/js-objects

<!-- SECTION lecture notes 11/3/22 -->

notes in PATH: Source/Codeworks/zookeeper
-good example of setTimeout() and also css animation

cubic-bezier.com : shows animation options

disable context-menu -- 

re-read: https://codeworksacademy.com/fs-student-guide/resources/wk2/06-Coding-Mistakes
Look up: ESLint and Prettier

Look up: single-threaded environments, stack structure, config file?

<!-- ANCHOR Week 3 -->
11/7/22

<!-- NOTE terminology: transpile -->

HW: section 1 of advanced-javascript videos
https://training.codeworksacademy.com/course/advancing-with-javascript/enroll?code=TUPC5-WQAY7

figjam: figma light

MVC(S): design pattern (model view controller service) organizing code to create a scalable project

View: html representation of data in app
Controller: Takes in actions from user, draws data to DOM (only thing user ever has access to)
Service: Business logic happens (anything that modifies data)
Appstate: single source of truth or where all the app's data will be stored
Model: blueprint of what the data in the appstate will look like @param {type} paramVar


in terminal: bcw create TEMPLATE

<!-- NOTE notes in /combatTracker -->

default type button in form is submit

<!-- SECTION 11/8/22 -->

exporting just an instance of service makes the service class untouchable by the user

in template, utils: writer.js setTEXT and setHTML

bs class to make hover awesome: "selectable"
html: title='name or whatever you want user to see' gives you info on mouseover

template variables go into the appState.js: get methods with this.key

activeGachamon var in appState = null

register a listener: in controller that listens for changes in the appSTate

<!-- NOTE this is the logic -->
watch activeGachamon and if it changes, draw it

appState.on('activeGachamon', this.drawActive) <!-- no parens -->

set triggers the listener (set is an equal sign)

add to array using equal sign: spread operator (...); when placed before a collection, it takes things out of the collection

data format for large arrays: objects (parameters in class draw from object)

css filter: hue-rotate, invert (alter colors)

appState.emit('thing listener is attached to')

codepen.io: go from SAwesomeCSS to CSS and back

<!-- SECTION 11/9/22 -->

notes in Source/CodeWorks/craigslist-site

Alerts! sweetalert2.github.io; Pop.js 

<!-- NOTE declare method -->
cmmd period on undeclared method

cmmd click on method or class name takes you to it

remove car with filter:
give me a new array of cars with all the cars that have ids that DON'T match the one I passed in

FormHandler: let formData = getFormData(form)

BootStrap Modals: paste in underneath the footer

js Date module: this.createdAt = new Date()
string interp: this.createdAt.toLocaleDateString()

static means a method that only exists on the class before it's been instantiated (grab something off the model)

<!-- SECTION 11/10/22 -->

Steps 
1. makes files: Model, Controller, Service
2. Build model (constructor and get template method) and export it
3. AppState -- create data
4. Controller -- export class, create constructor (log the connection)
5. Service -- export instance (log the connection)
6. App.js -- create instance of Controller class
7. Create _draw function in Controller (create id in index file)
8. Block out actual template in html and place in template getter in model
9. Block out form
10. Create onsubmit "createData()"function to call in the form
11. Do something with form data -- pass it to service to add it to your array of objects
12. Handle the form Data, turn into an object of Object class in Service,
13. Set event listener on array to draw when something changes


get Computed... (property on this that performs an action and returns a static)

.toLowerCase/uppercase 
get rid of commas and punctuation, RegEx and .replace 
website about RegEx 'regexr.com'

Logic: unlocking active case -- obj key (unlocked: false), change unlocked to true and emit active case (unlockActiveCase), if prompt returns true, drawCase, if prompt returns true, 

saveCase() -- textarea innerText is .value, attribute readonly unless unlocked

saveState -- whenever obj Array changes 
loadState -- in appState params: key, format and class

Double check: unlock/save button


