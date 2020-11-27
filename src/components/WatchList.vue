<template>
  <div id="watch-list">
      <h2>Watch List:</h2>
      <ul id="film-watch-list">
          <li v-for="(film, index) in watchList" v-bind:key="index">
              <span id="film-name">{{film.title}}</span>
              <br>
              <span id="film-release">Year Released: {{film.release_date}}</span>
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
    name: 'watch-list',
    props: ['watchList']
}
</script>

<style>

</style>