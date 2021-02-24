<template>
<div>
  <h1>Character list</h1>
  <div>
    <character-list :characters='characters'></character-list>
    <character-detail :character="selectedCharacter" ></character-detail>
  </div>
</div>
  
</template>

<script>
import CharacterList from './components/CharacterList.vue';
import CharacterDetail from './components/CharacterDetail.vue';

import {eventBus} from './main.js'

export default {
 name: 'app',
 data() {
   return {
     characters: [],
     selectedCharacter: null
   };
 },
 mounted() {
   fetch('https://rickandmortyapi.com/api/character/')
    .then(res => res.json())
    .then(data => this.characters = data.results)

    eventBus.$on('character-selected', (character) => {
        this.selectedCharacter = character
    })
 },
 components: {
     "character-list": CharacterList,
     "character-detail": CharacterDetail
 }
}
</script>

<style>

</style>
