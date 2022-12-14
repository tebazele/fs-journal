# MVC

<!-- #region [DECEMBER NOTES] -->
<!-- SECTION Nov 28, 2022 -->

Express is a server framework -- castle
Node runs your javascript --island

Knight is the http request
response comes back through the PORT

ORM -- goblin (takes request and sorts it out from the database and brings it)

middleware: guard outside the castle (checkpoint in hallways that knight has to pass through like API key, login (bearer token), error handler (gives ticket/status 404), helmet (deletes elements about the server from the 'header' that you don't want client to have), body-parser (axios turns stuff into a giant string--JSON parse that for me)

Network requests: 

cybersecurity -- develop code like you're going to be attacked

npmjs.com (cool stuff people have written that you can download)
express -- dependent on this for server

linting: formats code to practice 

<!-- STUB important -->
npm run start -- does same thing as node index.js but you run it in vs code and have a pause, start, stop buttons

Invalid Auth0 config: fix error by coming to main.js and comment out Auth0Provider.configure function

comment DbConnection.connect() so it doesn't try to connect to database
re-spin button

localhost:3000

every method inside class takes in three params: request, response, next

go into DbContext.js and comment out stuff at top of DbContext class

make post request from the console: postman.co

DEBUG: can't use debugger or console.log most of the time; 
lowercase logger from utils logger, use red dots on left side of code 

delete: check if it exists before trying to delete it

<!-- STUB start server in vs code -->
go into debugger modal and click "start server"


<!-- NOTE notes in Source/Codeworks/burgerShack -->

<!-- SECTION Nov 29, 2022 -->
gregslist again 

<!-- STUB [CONNECT MONGO DB] -->
connect MongoDB: put connection url with password and account name into .env (environment variables) under connection string

<!-- STUB [CONNECT AUTH 0] -->

auth0.com 
AUTH_DOMAIN=jeanne-allen.us.auth0.com
AUTH_AUDIENCE=https://jeannecoursework.com
AUTH_CLIENT_ID=sqlbSe3a1IkpDUog43u7KloBLXDFMzBT

domain and client are under applications > applications (click into)
audience is under application > apis

<!-- FIXME -->
TEST auth 0: go to localhost 3000

Mongoose Schema virtuals -- 

<!-- NOTE notes in Source/Codeworks/gregslist-node -->

including how to handle pagination and sort by query params

<!-- SECTION Nov 30, 2022 -->

add information to schema with virtuals (getter)
toJSON: { virtuals: true } (enables virtuals on the schema)

postman: put baseUrl in variables and include {{baseUrl}}

<!-- STUB auth0 -->
auth0: access middleware with .use method
Middleware test: .use((req,res,next)=> { logger.log(req); next() } ) -use is above the post and below the get, so we go through it (people can't create class unless they're an authorized user)

.use(Auth0Provider.getAuthorizedUserInfo)

tokens: must get a token onto our request in postman to authorize our code

inside client  > app > env.js (put .env info there)
both front end and back end talk to auth0 

postman auth: bearer token

auth rules -- read auth0 docs
inspect Preview: userinfo comes from auth0, account comes from our database

mongo id: object id
coachId: type: Schema.Types.ObjectId, ref: 'Account'(name of database in dbcontext) (whoever created the class gets a special id and gets to add people)
This class points back to the AccountsSchema

<!-- STUB [Data Relationships] -->

First data relationship: class is child of the coach

ClassSchema.virtual('coach', {
    localField: 'coachId', - what on this schema to look at
    foreignField: '_id', - what on the ref model to look at
    ref: 'Account', what model to look at
    justOne: true
})

in ClassesService next to .find, .populate('coach', 'only include this')
await populate because it does make more database requests

Many to many: Matches

go from player up to the matches .get('/:id/matches') -- called from Player controller to matches service

OR mongo way: { $or: [{}, {}] } -- this is very specific to mongoose
query casting (mongodb manual)

when posts load, we want the delete button to 

post.userId === userInfo of the person who's logged in

<!--  -->

<!-- #endregion -->

<!-- #region [DECEMBER NOTES] -->

<!-- SECTION Dec 1, 2022 -->

BirdBrain: 
1. .env 
2. init repo, invite collabs, clone down
3. set up schema in backend
4. register schema in dbcontext
5. create controller.js
6. create service.js
7. should you have to be logged in to create? Yes, 

.use(Auth0Provider.getAuthorizedUserInfo)
req.body.peeperId = req.userInfo.id

8. Start building front end (client > app)
9. Create client-side model

enum in mongoose: type--string, array of valid values
 <!--NOTE do maxlength on strings  -->

10. store in appState
11. create and link up Controller and Service
12. SCSS is compiled version of CSS, so we need to run SCSS:
write your CSS in main.scss
npm i bootstrap
npm run sass

13. Create index template and put in model 
CSS tutorial: img-fluid uses width and object fit
in your img class:
    width: 100% & height: set height 45vh, sometimes object-fit: cover
<!-- FIXME how to get peeper image from peeper ID?  -->
create virtual on schema, bird.populate in service
14. set listener: appstate.on
15. modal: put id on modal-content div, grab everything in between and set into Static Template in model
16. make an active bird template in model (On modal button: data-bs-toggle='modal' data-bs-target='#id of modal')
17. write activeBird method in controller and service and store in appState

Account to Bird is many to many: 
One account posts the bird and others say, "I've also seen that bird" -- CreepSchema is the glue that connects accounts to bird

mongo: findOne({birdId: body.birdId, creepId: body.creepId}) 

<!-- STUB look into mongodb create index -->
Schema.index({creepId: 1, birdId: 1}, unique) - create a unique index -- this will prevent us from created the same follow more than once

.get('/:birdId/creeps') - getCreepsByBirdId

creepCount goes on Bird Schema -- in virtual: count: true

CreepsService--getCreeps using string interpolation

CreepsController-- 

<!-- SECTION December 5, 2022 -->

Vue notes

<!-- SECTION December 12, 2022 -->
Some notes in PostIt

one to many: creator to albums, album to pictures
many to many: collaborators to albums

postman tests: validates if the code is good

<!-- NOTE bcw create fullstack open -->
1. cd into project then type:
code postIt.code-workspace

This is two separate projects in the same folder (workspace)
2. .env in server and env.js in client -- fill out
3. Spin up both servers
4. Login
5. Write schema in backend
(enum: ['', ''], lowercase: true) 
<!-- FIXME double check mongodb schema formatting for getting to lowercase -->
6. Write this.router.get.post etc in controller
delete is archive: (archived: delete without deleting)
- pass in req.params.id & req.userInfo.id 
- reuse getOne test (fail first and fail fast)
- we don't have to delete it even if it's a delete route
- flip bool, album.save() -- .save built into the mongoose documents
7. Test in PostMan 
(change your code, not the code in postman)
middleware will get you your req.body.creatorId = req.userInfo.id

<!-- NOTE don't forget await -->

Restful conventions: 
better to make many small requests than one big one

ask Album controller for pictures but not the album itself 
* picturesController: sends a query into the getAll
* albums controller: sends the query { albumId: id, ...req.query }

both ways are supported by api (api/album/:id/pictures & api/pictures?albumId=id / api/pictures?creatorId=id)

<!-- NOTE limit data -->
find(with param)
.limit(10).skip(page*10) quick and dirty pagination

AlbumsSerivce 
pass in req.query.page in controller

albumsService - return object with results as a key value pair

.equals -- mongoose thing

postman import link (paste in link)

if the request is broken, we never get to the tests

<!-- NOTE testing framework: mocha & chai -->

<!-- SECTION Dec 13, 2022 -->
When you clone down, run npm i in both client and server folders

8. write front-end getter
9. dump to page -- clean up

PostIt Homepage: @click="filter='animals'"
filterBy = ref('') - in setup

albums: computed(( => {
    if (filterBy.value == '') {
        return AppState.albums
    } else {
        return.AppState.albums.filter(a => a.cateogry == filterBy.value)
    }
}))

<!-- NOTE set up router link review -->
1. put <router-link></router-link> tag around clickable component
2. create page to route to
3. set up path in router.js


 NODE: .find vs .findById --
 find by Id finds one by the _id field specifically

 .find(argument) finds all with that value


<!-- NOTE reusable form on modal - swap out  -->

components > ModalComponent (put bootstrap modal in there)
navbar component (add modal button)
component > albumform (put everything inside modal content in here)
components > modalComponent <slot></slot> in another component inside this component
put component tag inside other component tag on page 

you can have more than one slot--syntax

<!-- NOTE hide modal after the form submits -->
import modal from bootstrap: 
Modal.getOrCreateInstance('#exampleModal').hide()

Default on backend is to add to bottom of the database (.sort by createdAt if you want things to be added to the top)

<!-- FIXME review mongodb sort  -->

router push in Modal form 

masonry -- diff image heights that stack nicely (postIt figma)

No account on refresh? -- authService - place stuff here that you want to run 


<!-- #endregion -->

