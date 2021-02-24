<template>
<div>
  <ul>
    <item-list v-for="(character, index) in character" :character=character :key="index"></item-list> 
  </ul>
</div>
  
</template>

<script>
import ItemList from './ItemList.vue'

export default {
  name: 'character-list',
  props: ['character'],
  components: {
    "item-list": ItemList
  }
}
</script>

<style>

</style>