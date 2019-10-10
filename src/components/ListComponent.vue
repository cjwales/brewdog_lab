<template lang="html">
  <div>
    <li v-on:click="handleClick">{{beer.name}}</li>
  </div>
</template>

<script>
import {eventBus} from '../main.js'
export default {
  name: 'list-component',
  props: ['beer'],
  methods: {
    handleClick() {
      eventBus.$emit('selectedBeer', this.beer)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
