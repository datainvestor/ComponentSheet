<template>
  <div class="hello">

    <h1 v-if="isList">This is id {{id}} of the todo {{ dynamicmsg }}</h1>
    <h1 v-else> {{ dynamicmsg }} </h1>
  </div>
</template>

<script>
//  Here we pass static value as prop
// To use propo in computed call this.id, this.dynamicmsg
export default {
  name: 'DynamicProp',
  props: ["id","dynamicmsg", "isList"],
}
</script>

<style scoped>
</style>
