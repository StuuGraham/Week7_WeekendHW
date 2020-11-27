<template>
  <div id="app">
    <h1>Studio Ghibli Film Tracker</h1>
    <div class="main-container">
      <films-list :films="films"></films-list>
      <film-detail :film="selectedFilm"></film-detail>
  </div>
  <button v-if="!watchList.includes(selectedFilm)" v-on:click="addToWatchList">Add This Film Your Watch List</button>
  <watch-list :watchList="watchList"></watch-list>
  <favourite-films :favouriteFilms="favouriteFilms"></favourite-films>
  </div>
</template>

<script>
import FilmList from './components/FilmList.vue';
import FilmDetail from './components/FilmDetail.vue';
import WatchList from './components/WatchList.vue';
import FilmFaves from './components/FilmFaves.vue';

// FilmSelect No Longer Necessary.
// import FilmSelect from './components/FilmSelect.vue';

import {eventBus} from './main.js';

export default {
  name: 'App',
  data() {
    return {
      films: [],
      selectedFilm: null,
      watchList: [],
      favouriteFilms: []
    };
  },

  mounted() {
    fetch('https://ghibliapi.herokuapp.com/films')
    .then(res => res.json())
    .then(films => this.films = films);

    eventBus.$on('film-selected', (film) => {
      this.selectedFilm = film;
    })

  },
  methods: {
    addToWatchList: function() {
      if(this.watchList.indexOf(this.selectedFilm) === -1) {
        this.watchList.push(this.selectedFilm);
      }
    },

    addToFavourites: function() {
      if(this.favouriteFilms.indexOf(this.selectedFilm) === -1) {
        this.favouriteFilms.push(this.selectedFilm);
      }
    }
  },
  components: {
    'films-list': FilmList,
    'film-detail': FilmDetail,
    'favourite-films': FilmFaves,
    'watch-list': WatchList
  },
}
</script>

<style>

</style>
