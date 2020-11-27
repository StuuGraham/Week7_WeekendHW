<template>
  <div v-if="film">
      <h3>{{film.title}}</h3>
      <br>
      <p>{{film.description}}</p>
      <p>Year Released: {{film.release_date}}</p>
      <p>Directed By: {{film.director}}</p>
      <br>
      <p>Rotten Tomatoes Score: {{film.rt_score}}%</p>
  </div>
</template>

<script>
export default {
    name: 'film-detail',
    props: ['film']
}
</script>

<style>

</style>