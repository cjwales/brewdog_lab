<template lang="html">
  <div>
    <li>{{beer.name}}</li>
  </div>
</template>

<script>
export default {
  name: 'list-component',
  props: ['beer']
}
</script>

<style lang="css" scoped>
</style>
