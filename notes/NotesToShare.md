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