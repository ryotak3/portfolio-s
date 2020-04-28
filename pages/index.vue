<template>
  <b-carousel
    v-model="carousel"
    :pause-hover="false"
    :autoplay="true"
    :repeat="true"
    :interval="interval"
    :animated="animated"
    :indicator="false"
  >
    <b-carousel-item v-for="(carousel, i) in carousels" :key="i">
      <a class="image vwmax" @click="goPhotography(carousel.category)">
        <!-- <img :src="carousel.img" /> -->
        <img v-lazy="carousel" alt="" />
      </a>
    </b-carousel-item>
  </b-carousel>
</template>

<script>
import moment from 'moment';
import { createClient } from '~/plugins/contentful.js';
import loading from '~/assets/loader.gif';

const client = createClient();
export default {
  transition: 'slide-left',
  filters: {
    moment(value, format) {
      return moment(value).format(format);
    }
  },
  asyncData({ env, params }) {
    return client
      .getEntries({ content_type: env.CTF_BLOG_POST_TYPE_ID })
      .then(entries => {
        return {
          posts: entries.items
        };
      })
      .catch(console.error);
  },
  data() {
    return {
      carousels: [
        { category: 'street', src: 'street.jpg', loading },
        { category: 'portrait', src: 'portrait.jpg', loading },
        { category: 'landscape', src: 'landscape.jpg', loading },
        { category: 'cycling', src: 'cycling.jpg', loading },
        { category: 'live', src: 'live.jpg', loading },
        { category: 'stilllife', src: 'stilllife.jpg', loading }
      ],
      pauseType: 'is-primary',
      interval: 5000,
      animated: 'fade'
    };
  },
  methods: {
    goPhotography(index) {
      this.$router.push({ path: `/photography/`, query: { v: index } });
    }
  }
};
</script>
<style>
/* 全画面表示のための設定 */
body {
  overflow: hidden;
}
.vwmax {
  height: 100vh;
  width: auto;
  margin: 0 -500%;
  padding: 0;
  overflow: hidden;
}
.vwmax img {
  width: auto;
  height: 100vh;
  position: relative;
  top: 50%;
  left: 50%;
  -webkit-transform: translate(-50%, -50%);
  -ms-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
}
</style>
