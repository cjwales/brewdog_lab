<template lang="html">
  <div>
    <ul>
      <li v-for="favourite in favourites">{{favourite.name}}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'favourite-beers',
  props: ['favourites']
}
</script>

<style lang="css" scoped>
</style>
