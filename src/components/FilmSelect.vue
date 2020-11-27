This file now redundant after changing to a dropdown system in FilmList.vue

<template>
  <li v-on:click="handleClick">{{film.title}}</li>
</template>

<script>
import {eventBus} from '../main.js'
export default {
    name: 'selected-film',
    props: ['film'],
    methods: {
        handleClick() {
            eventBus.$emit('film-selected', this.film);
        }
    }
}
</script>

<style>

</style>