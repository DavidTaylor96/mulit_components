<template>
<div>
  <select v-on:change="handleSelect" v-model="selectedCharacter">
    <option v-for="(character, index) in characters" :value="character" :key="index">{{character.name}}</option> 
  </select>
</div>
</template>

<script>
import {eventBus} from '../main.js'

export default {
    data() {
    return {
      selectedCharacter: {}
    }
  },
  props: ['characters'],
  
  methods: {
    handleSelect() {
      eventBus.$emit('character-selected', this.selectedCharacter)
    }
  }
}
</script>

<style>

</style>