<template>
  <div class="hello">

    <h1> Passing author name: {{author.name }} of book: {{author.company}} </h1>
    
  </div>
</template>

<script>
//  Here we pass static value as prop
export default {
  name: 'ObjectProp',
  props: ["author"]
}
</script>

<style scoped>
</style>
