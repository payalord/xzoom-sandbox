<template>
  <h1>Vue.js example with xZoom</h1>
  <p>Please check <a href="https://vuejs.org" target="_blank">vuejs.org</a> for more information about Vue</p>
  <img alt="Vue logo" src="./assets/logo.png" />
  <xzoom :images="images" :options="options" />
</template>

<script>
import xzoom from "./components/xzoom";

export default {
  name: "App",
  data: function () {
    return {
      images: [
        {
          thumb: require('./assets/gallery/thumbs/01_b_car.jpg'),
          preview: require('./assets/gallery/preview/01_b_car.jpg'),
          original: require('./assets/gallery/original/01_b_car.jpg')
        },
        {
          thumb: require('./assets/gallery/thumbs/02_o_car.jpg'),
          preview: require('./assets/gallery/preview/02_o_car.jpg'),
          original: require('./assets/gallery/original/02_o_car.jpg')
        },
        {
          thumb: require('./assets/gallery/thumbs/03_r_car.jpg'),
          preview: require('./assets/gallery/preview/03_r_car.jpg'),
          original: require('./assets/gallery/original/03_r_car.jpg')
        },
        {
          thumb: require('./assets/gallery/thumbs/04_g_car.jpg'),
          preview: require('./assets/gallery/preview/04_g_car.jpg'),
          original: require('./assets/gallery/original/04_g_car.jpg')
        }
      ],
      options: {
        tint: '#333',
        Xoffset: 15
      }
    };
  },
  components: {
    xzoom,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
