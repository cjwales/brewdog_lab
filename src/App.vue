<template lang="html">
  <div>
    <h1>Brewdog Beers</h1>
    <div class="main-container">
      <beers-list :beers="beers"></beers-list>
      <favourite-beers :favourites="favourites"></favourite-beers>
      <beer-detail :beer="selectedBeer"></beer-detail>
    </div>
  </div>
</template>

<script>
import {eventBus} from './main.js'
import BeersList from './components/BeersList.vue'
import ListComponent from './components/ListComponent.vue'
import BeerDetail from './components/BeerDetail.vue'
import FavouriteBeers from './components/FavouriteBeers.vue'

export default {
  name: 'app',
  data(){
    return {
      beers: [],
      favourites: [],
      selectedBeer: null
    }
  },
  mounted() {
    fetch('https://api.punkapi.com/v2/beers')
    .then(res => res.json())
    .then(beers => this.beers = beers)

    eventBus.$on('selectedBeer', (beer) => {
      this.selectedBeer = beer;
    })

      eventBus.$on('selectedFavourite', (favouriteBeer) => {
      this.favourites.push(favouriteBeer)

    })
  },
  components: {
    "beers-list": BeersList,
    "list-component": ListComponent,
    "beer-detail": BeerDetail,
    "favourite-beers": FavouriteBeers
  }
}
</script>

<style lang="css" scoped>
.main-container {
  display: flex;
}
</style>
