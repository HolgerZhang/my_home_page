<template>
  <div class="position-relative justify-content-center align-content-center text-center p-2 m-5"
       style="color: lightgray; line-height: 2;">
    <div class="copyright">&copy; {{ year }} | By {{ author }}.</div>
    <div class="footer_custom_text">
      <div><a href="http://beian.miit.gov.cn/" target="_blank" rel="nofollow noopener">{{ ipc }}</a></div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Footer",
  props: {
    year: Number,
    author: String,
    ipc: String
  }
}
</script>

<style scoped>
a {
  color: #2196f3;
}
</style>
