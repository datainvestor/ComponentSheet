<template>
  <div class="hello">
 <!-- Or put multiple clases in a list ["classtag, otherclass"] -->
 <!-- this works with other attributes than class but need to remembver using ":" -->
    <h1 :class="classtag"> Color change text </h1>
    
  </div>
</template>

<script>
//  Here we pass static value as prop
export default {
  name: 'ClassProp',
  props: ["classtag"]
}
</script>

<style scoped>
.colored {
  color:aquamarine
}
</style>
