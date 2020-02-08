<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
  </div>
</template>

<script>
//  Here we pass static value as prop
export default {
  name: 'StaticProp',
  props: {
    msg: String
  } //  can also be props: ["msg"]
}
</script>

<style scoped>
</style>
