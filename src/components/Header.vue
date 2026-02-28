<template>
  <div>
    <div id="header"
       class="flex mx-auto justify-content-center place-items-center items-center p-6 text-4xl"
       style="justify-content: center; align-items: center; font-weight: 600">
    <h2 class="flex items-center p-6 text-4xl header-text-color" style="z-index: 1;">
    <font-awesome-icon class="inline-block align-middle mr-4 header-icon-gradient" :icon="['fa', 'cubes']" style="z-index: 1"/>
    <span>{{ msg }}</span>
    </h2>
    </div>
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
.header-text-color {
  background: linear-gradient(90deg,#188dcc 20%,#b754ed 80%);
  background-clip: text;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  text-align: center;
}

.header-icon-gradient::v-deep svg,
.header-icon-gradient::v-deep path {
  fill: #188dcc !important;
}
</style>
