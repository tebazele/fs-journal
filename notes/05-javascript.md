# JavaScript

<!-- #region (collapsed) [notes October] -->
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
<!-- #endregion -->

<!-- #region (collapsed) [notes November] -->
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

<!-- SECTION notes 11/14/22  -->
Asynchronous code 
notes in Source/Codeworks/hpTradingCards
<!-- NOTE working with apis -->

hp-api : Harry Potter api

herokuapp - someone's hosting an api for you, network tab shows JSONified data

response.json(): Note that despite the method being named json(), the result is not JSON but is instead the result of taking JSON as input and parsing it to produce a JavaScript object.

Network tab: what files did my computer need to render stuff

cards Service is the one who actually grabs the data from api

const response = await fetch('api url')

http.cat : Status

script:axios - library that makes fetch requests easier

response.data is just pojos, we need to map to class Card
.map(cardData => new Card(dardData))

domain.com/(route parameter)

async functionName() {
    try {
        this.
    }
    catch (error) {
        report error message
    }
}

catch stops the code from running the next line and reports the error
<!-- NOTE network requests should begin in a try catch -->

opentdb.com/api_config.php (Trivia api)

check object for data key


<!-- SECTION notes 11/15/22 -->
schema: https://bcw-sandbox.herokuapp.com/ (/api/cars)

in controller:
async methodName() {
    try {
        await //do something, get data...
    } catch (error) {
        Pop.error or console.log(error)
    }
}

In service:
const response(res) = await axios.get(url)

async createCar() {
    window.even.preventDefault()

}

axios.get
add: axios.post
axios.delete('url' + id(id was passed in as the parameter))
edit: axios.put(url + id, send new data)

async/await -- use when your code leaves your machine or the load time is out of your control

<!-- SECTION notes 11/16/22 -->
Multiple apis: 

take data from api and make it your own api/name/data
<!-- NOTE  do this in the service-->
axios instance: const variable = axios.create({
    baseURL: ''
})



dndApi.get()

Step 1: get objects from api
Step 2: write constructor for model

Add and remove spells from myspells
- add a button, grab activespell from spells array and push it as a Spell object to my api and my array and redraw myspells

'Add' on spells from original api
'remove' on spells from myspells

get ComputeButtons()

for checkboxes: onchange="function()", checked attribute

const res = axios.put(is, data)

<!-- SECTION Notes 11/17/22 -->

use the Network tab
api.nasa.gov (picture of the day)

Api Key: generate api key, 

Start by created axios.create instances for apis you're interacting with;
grab from an api and save to your sandbox api

axios.create({
    baseURL: '',
    timeout: 8000, (send me an error if this is taking forever),
    params: {api_key: 'mykey'}
})
axios looks for params and tacks them on the end of the base url

CSS tip: on hover for one elem, target another element: +
nasa-apod lecture

html input: type=date (in js: grab date picker, set value to today's date and max-value to today's date, format to how our api date is: toISOString, .substring(0, 10))
<!-- FIXME  -->
turn null checks back on

I don't need to pull the apods back down from my sandbox as is, they're more like bookmarks to the actual api

you can target your offCanvas "bootstrap.OffCanvas"


<!-- #endregion -->
