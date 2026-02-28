<template>
  <div class="page-bg">
    <div class="container mx-auto flex flex-col min-h-screen">
      <Header :msg="msg"/>
      <div class="flex-1 flex flex-col justify-center">
        <div class="grid grid-cols-1 lg:grid-cols-3 ">
          <CardView class="m-5"
                    v-for="(site, i) in webSites" :key="i"
                    :index="site.index"
                    :fas="site.fas"
                    :title="site.title"
                    :desc="site.desc"
                    :link="site.link"/>
        </div>
      </div>
      <div class="mt-auto">
        <Footer author="HOLGER ZHANG" ipc="黑ICP备20001742号" :year="currentYear"/>
      </div>
    </div>
  </div>
</template>

<script>
import CardView from "@/components/CardView";
import Header from "@/components/Header";
import Footer from "@/components/Footer";

export default {
  name: 'HelloWorld',
  components: {Footer, Header, CardView},
  props: {
    msg: String
  },
  computed: {
    currentYear() {
      return new Date().getFullYear()
    }
  },
  data: () => {
    return {
      webSites: [{
        index: '01',
        fas: 'fa-book',
        title: "Holger's Blog",
        desc: '心有所向 日复一日 必有精进',
        link: 'https://blog.holger.host'
      }, {
        index: '02',
        fas: 'fa-robot',
        title: 'About Me',
        desc: '关于我',
        link: 'https://me.holger.host'
      }, {
        index: '03',
        fas: 'fa-camera',
        title: 'Travel',
        desc: '旅行日志',
        link: 'https://travel.holger.host'
      }]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>

@keyframes gradient-shift {
  0% { background-position: 0% 0%; }
  25% { background-position: 100% 15%; }
  50% { background-position: 90% 90%; }
  75% { background-position: 10% 85%; }
  100% { background-position: 0% 0%; }
}

body {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  margin: 0;
}

.page-bg {
  min-height: 100vh;
  width: 100%;
  min-width: 100vw;
  box-sizing: border-box;
  /* 浅色动态渐变，不均匀色标 + 非线性动画 */
  background: linear-gradient(
    135deg,
    #fef9f3 0%,
    #d4e9f7 12%,
    #e8dcef 35%,
    #d4f0e0 62%,
    #f5eef6 85%,
    #fef9f3 100%
  );
  background-size: 320% 320%;
  animation: gradient-shift 10s cubic-bezier(0.45, 0, 0.55, 1) infinite;
}
</style>
