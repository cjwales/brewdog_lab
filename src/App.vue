<template lang="html">
  <div>
    <h1>Brewdog Beers</h1>
    <beers-list :beers="beers"></beers-list>
  </div>
</template>

<script>
import BeersList from './components/BeersList.vue'
import ListComponent from './components/ListComponent.vue'

export default {
  name: 'app',
  data(){
    return {
      beers: []
    }
  },
  mounted() {
    fetch('https://api.punkapi.com/v2/beers')
    .then(res => res.json())
    .then(beers => this.beers = beers)
  },
  components: {
    "beers-list": BeersList,
    "list-component": ListComponent
  }
}
</script>

<style lang="css" scoped>
</style>
