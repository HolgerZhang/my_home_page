<template>
  <div class="container mx-auto">
    <Header :msg="msg"/>
    <div class="grid grid-cols-1 md:grid-cols-2 xl:grid-cols-3 ">
      <CardView class="m-5"
                v-for="(site, i) in webSites" :key="i"
                :index="site.index"
                :fas="site.fas"
                :title="site.title"
                :desc="site.desc"
                :link="site.link"/>
    </div>
    <Footer author="Holger Zhang" ipc="黑ICP备20001742号" :year="2022"/>
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
  data: () => {
    return {
      webSites: [{
        index: '01',
        fas: 'fa-book',
        title: 'Holger 小站',
        desc: '整理知识，记录成长。',
        link: 'https://blog.holgerbest.top/'
      }, {
        index: '02',
        fas: 'fa-file-download',
        title: '下载站 Get',
        desc: '小文件共享下载站。公共用户请关注公众号“Holger Learning”获取！',
        link: 'https://get.holgerbest.top/'
      }, {
        index: '03',
        fas: 'fa-atlas',
        title: '导航 StartUP',
        desc: '仿 夸克浏览器 的轻量级导航。',
        link: 'https://startup.holgerbest.top/'
      }, {
        index: '04',
        fas: 'fa-book',
        title: 'API',
        desc: '实验性 API 分发站点。',
        link: 'https://api.holgerbest.top/'
      }, {
        index: '05',
        fas: 'fa-music',
        title: '在线音乐播放器',
        desc: '轻量级可嵌入的 JS 音乐播放器（需将 mp3 链接传入 URL 参数 music）',
        link: 'https://play.holgerbest.top/?music=example'
      }, {
        index: '06',
        fas: 'fa-warehouse',
        title: '私有存储仓库 Repo',
        desc: '私有存储仓库，现用于全站图片、PDF存储。',
        link: 'https://repo.holgerbest.top/'
      }]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>

body {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  background: #161623 !important;
}

body::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(#f00, #f0f);
  clip-path: circle(10% at right 70%);
}

body::after {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(#2196f3, #e91e63);
  clip-path: circle(20% at 10% 10%);
}
</style>
