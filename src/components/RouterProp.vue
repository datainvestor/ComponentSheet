<template>
  <div class="hello">
    <h1>{{ name }}</h1>
  </div>
</template>

<script>
//  Here we pass static value as prop
export default {
  name: 'RouterProp',
  props: ["name"]
}
</script>

<style scoped>
</style>
