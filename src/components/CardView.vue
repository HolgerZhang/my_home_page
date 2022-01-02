<template>
  <a :href="link" target="_blank">
    <div class="my-container">
      <div class="card backdrop-filter backdrop-blur-lg">
        <div class="content">
          <h2>{{ index }}</h2>
          <h3>
            <font-awesome-icon :icon="fas.split('-', 2)"/>
            {{ title }}
          </h3>
          <p>{{ desc }}</p>
          <a :href="link" target="_blank">GO</a>
        </div>
      </div>
    </div>
  </a>
</template>

<script>
import VanillaTilt from 'vanilla-tilt';

export default {
  name: "CardView",
  props: {
    index: String,
    fas: String,
    title: String,
    desc: String,
    link: String
  },
  mounted() {
    VanillaTilt.init(document.querySelectorAll('.card'), {
      max: 25,
      speed: 400,
      glare: true,
      "max-glare": 1
    })
  }
}
</script>

<style scoped>
.my-container {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  max-width: 800px;
  flex-wrap: wrap;
  z-index: 1;
}

.my-container .card {
  position: relative;
  width: 280px;
  height: 350px;
  margin: 30px;
  box-shadow: 20px 20px 50px rgba(0, 0, 0, .5);
  border-radius: 15px;
  background: rgba(255, 255, 255, .1);
  overflow: hidden;
  display: flex;
  justify-content: center;
  align-items: center;
  border-top: 1px solid rgba(255, 255, 255, .5);
  border-left: 1px solid rgba(255, 255, 255, .5);
  /*backdrop-filter: blur(10px);*/
}

.my-container .card .content {
  padding: 20px;
  text-align: center;
  transform: translateY(50px);
  transition: 0.5s;
}

.my-container .card:hover .content {
  transform: translateY(0);
}

.my-container .card .content h2 {
  position: absolute;
  top: -80px;
  right: 30px;
  font-size: 8em;
  color: rgba(255, 255, 255, .05);
  pointer-events: none;
}

.my-container .card .content h3 {
  font-size: 1.8em;
  color: white;
  z-index: 1;
}

.my-container .card .content p {
  font-size: 1em;
  color: white;
  font-weight: 300;
}

.my-container .card .content a {
  position: relative;
  display: inline-block;
  padding: 8px 20px;
  margin-top: 15px;
  background: white;
  color: black;
  border-radius: 20px;
  text-decoration: none;
  font-weight: 500;
  box-shadow: 0 5px 15px rgba(0, 0, 0, .2);
}

</style>
