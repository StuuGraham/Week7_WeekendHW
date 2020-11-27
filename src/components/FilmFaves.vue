<template>
  <div id="favourite-films">
      <h2>Favourite Films:</h2>
      <ul id="fave-film-list">
          <li v-for="(film, index) in favouriteFilms" v-bind:key="index">
              <span id="film-name">{{film.title}}</span>
              <br>
              <span id="film-release">Year Released: {{film.release_date}}</span>
              <br>
              <span id="film-director">Directed By: {{film.director}}</span>
              <br>
              <span id="film-producer">Produced By: {{film.producer}}</span>
              <br>
              <span id="film-desc">Synopsis: {{film.description}}</span>
              <br>
              <span id="film-rating">Rotten Tomatoes Score: {{film.rt_score}}%</span>
          </li>
      </ul>
  </div>
</template>

<script>
export default {
    name: 'favourite-films',
    props: ['favouriteFilms']
}
</script>

<style>

</style>