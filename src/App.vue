<template>
<div>
  <h1>Character list</h1>
  <div>
    <character-list :character='character'></character-list>
  </div>
</div>
  
</template>

<script>
import CharacterList from './components/CharacterList.vue'
export default {
 name: 'app',
 data() {
   return {
     character: [],
   }
 },
 mounted() {
   fetch('https://rickandmortyapi.com/api/character/')
   .then(res => res.json())
   .then(character => this.character = character)
 },
 components: {
     "character-list": CharacterList,
 }
}
</script>

<style>

</style>
