<template>
  <div>
    <div v-if="!character">
      <p>Please select a character</p>
    </div>
    <div v-if="character">
      <h3>Name: {{character.name}}</h3>
      <p>Status: {{character.status}}</p>
      <p>Species: {{character.species}}</p>
       <img class="image" :src="character.image">
    </div>
  </div>
</template>

<script>
export default {
  name: 'character-detail',
  props: ['character']
}
</script>

<style>

</style>