<template>
 <option>{{character.name}}</option> 
</template>

<script>
import { eventBus } from '../main.js'

export default {
  name: 'item-list',
  props: ['character'],
}
</script>

<style>

</style>