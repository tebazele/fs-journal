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


