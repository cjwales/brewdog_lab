<template lang="html">
  <div v-if="beer" class="beer-detail">
    <h3>{{beer.name}}</h3>
    <h4>{{beer.tagline}}</h4>
    <h5>ABV: {{beer.abv}}</h5>
    <h5>First Brewed: {{beer.first_brewed}}</h5>
    <p>About this beer: {{beer.description}}</p>
    <img :src="beer.image_url">
    <button type="button" name="add-favourite">Add to Favourites</button>
  </div>
</template>

<script>
export default {
  name: 'beer-detail',
  props: ['beer']
}
</script>

<style lang="css" scoped>

.beer-detail {
  max-width: 300px;
}

img {
  max-height: 200px;
}

h4 {
  font-weight: normal;
}
</style>
