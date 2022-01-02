<template>
  <div id="header"
       class="flex mx-auto justify-content-center place-items-center items-center p-6 text-4xl"
       style="justify-content: center; align-items: center; color: white; font-weight: 600">
    <font-awesome-icon class="inline-block align-middle" :icon="['fa', 'cubes']" style="z-index: 1"/>
    <h2 class="flex items-center p-6 text-4xl " style="z-index: 1;">{{ msg }}</h2>
  </div>
</template>

<script>
export default {
  name: "Header",
  props: {
    msg: String
  }
}
</script>

<style scoped>

</style>
