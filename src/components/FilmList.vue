<template>
    <div>

        <!-- <ul>
            <selected-film v-for="(film, index) in films" :film="film" :key="index"></selected-film>
        </ul> -->

        <!-- Lines 4 -> 6 now redundant after changing to a dropdown system below. -->

        <label for="film_select">Select A Film:</label>
        <br>
        <select id="film_select" v-on:change="handleSelect" v-model="selectedFilm">
            <option disabled value="">Select A Film :)</option>
            <option v-for="(film, index) in films" :value="film" :key="index">{{film.title}}</option>
        </select>
    </div>
</template>

<script>
import {eventBus} from '../main.js'
import FilmSelect from './FilmSelect.vue'
export default {
    name: 'films-list',
    props: ['films'],
    data() {
        return {
            'selectedFilm': {},
        }
    },
    components: {
        "selected-film": FilmSelect
    },
    methods: {
        handleSelect() {
            eventBus.$emit('film-selected', this.selectedFilm);
        }
    }
}
</script>

<style>

</style>