# MVC

<!-- SECTION Dec, 5, 2022 -->

Reactivity: 

Angular or React are the other big ones

vuejs.org -- docs 

Homepage: html, js, css components

run npm i if it work

hot reloading

Different pieces of the app exist in different spots:
App.vue: header, main, footer template
import components from ... connects the stuff up

router vue: gets us from one pg to the next easily

How vue handles which page to show: 

SPA: single-page application, there's 1 pg and everything gets put into it dynamically

Vue only changes out the tiniest amount it needs to

Script tag is similar to how a class works (piece of js that is exported along with html component)

<!-- STUB Rules of view -->
1. for the template to access data in the script it must be in the return
2. for reactivity to take place, you must use vue's reactive stuff (vuePoints: ref(0)) import { ref } from 'vue' (creates a single reactive value)
3. pages are responsible for getting api data or getting the data they rely on displaying


pretty much, don't store variables on the homepage unless it literally only matters there; put it in the appState (vuePoints : computed(() => AppState.vuePoints))

v-on:click="" or @click

Instead of putting methods in onclick, write a method inside the setup() { class } and create a service and manipulate it (always return from setup uncalled function)

We have logger.log() on the frontend now
put parenthesis around only if passing an argument

can define non-async functions right in the return

if outside the return, considered private, inside return public

v-for="number in 10" inside a <div> get item 10 times

<!-- NOTE  -->
: is for interpolation in tags (non-content), {{}} is for interpolation between tags (content)

:disabled="vuePoints<= item.price" disabled is only included if condition is met

Inside components: create new view, put stuff in there

render <Shop /> html-tag-like thing that has name of my component

computed is like appstate.on

lifecycle hooks: onMounted(()=> )

<!-- SECTION Dec 6, 2022 -->

vue-flix 

<!-- NOTE look up docs to see how to handle keys and query params -->

Axios.create({
    params: {
        api_key: '',
        sort_by: 'popularity.desc', "certification.lt": 'r' (no r-rated movies)
    }
})
<!-- NOTE  inside script tag on HomePage.vue-->
export default {
  setup() {
    onMounted(() => {
      getMovies()
    })

    async function getMovies() {
      try {
        // create moviesService in services
        await moviesService.getMovies()
      } catch (error) {
        logger.error(error)
      }
    }
    return {
      movies: computed(() => AppState.movies)
    }
  }
}

get more results: pagination in url &page=2

you can set default parameters even if you don't pass anything

1. pull out component: 
replace in Homepage with exported <MovieCard (this is the name of the file) v-for="m in movies" (this is a prop--homepage will pass this value to the moviecard):banana='m'/>
2. in homepage (parent component), export Props (banana)
3. import props in MovieCard.vue (export default { props: {banana: String } }) (props is like a method that you are passing one param into--keyword for vue)
4. You don't have to return props in the export default setup() method: (define props above setup() )



CSS: input-group bootstrap class (attach button to input field

in SearchBar.vue:
v-model="(what you're tying into) search.query") -- in input field

const search = reactive({
    query: ''
})

or const search = ref('')

in moviesService -- get by query

on the html form: @submit.prevent
in Movies service get('search/movie', { params: search })

<!-- NOTE linking to other pages -->

router.js: 
routes: 
path: '/movie/:title',
name: 'MovieDetails',
component: loadPage('MovieDetails')

Pages are first to render to page and handle accessing services and apis
components are smaller chunks

<router-link> tag (creates an a tag) (we can supply the path with an :id or :title)

<router-link :to="{name:a;lsf {id: alf}}"
<!-- NOTE access from URL -->
access stuff from URL: above onMounted(), const route = useRoute()
route.params.id

vue 3 docs (router query) router push query

<!-- SECTION Dec 7, 2022 -->

Gregslist again

Spin up server separately

props: { car: { type: Object, required: true } }

ref instead of reactive: 
const formData = ref({
    make:
    model:
})

if you're using ref, must access formData.value
ref is meant for values (can be any type), reactive is meant for objects--it can react to specific changes

For props to exist inside setup, setup can take in props setup(props)


<!-- NOTE edit car -->
router push: (you have to click on a routerlink but not on a router push) 
top of setup() {
    const router = useRouter() -- don't forget to import useRouter
}
in return {
    gotTo() {
        router.push({name: 'CarDetails', params: {id: props.car.id } })
    }
}

call get functions in each page onMounted(() => function)

car?.make -- don't try to render it if it doesn't exist

<CarForm :carData='car"/> use props inside component tag 

put it in component above setup 
props: { carData: {type: Object, default:  },

(props.carData.id)

<!-- NOTE emit component tells parent that something has changed -->
setup(props, {emit}) emit caredited -- CarForm (child)
on car details page -- create own function  (parent)

you can chain emits but avoid it

1. Connect server to auth and DB with .env
2. Connect client to auth with env.js
3. Create CarsPage and hardcode car card into it
4. Create CarCard component
5. replace carcard html with <CarCard /> tag in CarsPage and send out prop
6. grab prop in component 



<!-- SECTION Dec 8, 2022 -->
Questions: 
1. v-model get data back into form to edit it
2. delay on refresh (CarDetails page still has old info in it (clear out AppState?))

<!-- NOTE pre-populate data into form:  -->

In account page: 
1. set up const editable = ref({})
2. watchEffect() (import this)
    if something in AppState.account.id changes, editable.value = {...AppState.account} (dumps stuff out of account and creates new object)
3. return out editable and v-model='editable.name' for everything in form
4. write put request

in return async editAccount() {
  try/catch
  accountsService.editAccount(editable.value)
}

<!-- NOTE model to see project images -->
App.vue is accessible to all pages
Put modal in there!

Make ModalComponent.vue and pop that into App.vue

activeProject in appState, 

in return in ProjectCard
setActiveProject(props.project)

v-if="project" on modal content

<!-- NOTE bigger modal -->
BiggerModal: modal-dialog modal-xl

<!-- NOTE check if someone stole my img -->
ProjectCard
includesMe: computed(()=> props.project.projectImgs.includes('AppState.account.picture'))

- css nth-child just supports odd and even
- it might be easiest to just write a python loop to add the class to the dom
- template += class

<!-- SECTION Dec 12, 2022 -->

Some notes in PostIt










