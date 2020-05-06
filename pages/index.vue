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
      <div class="contents">
        <a class="image vwmax" @click="goPhotography(carousel.category)">
          <img v-lazy="carousel" class="backimg" alt />
          <img class="logoimg" src="~assets/weekendcycler_logotype_2nd.png" alt="weekendcycler" />
        </a>
      </div>
    </b-carousel-item>
  </b-carousel>
</template>

<script>
import moment from 'moment';
import { createClient } from '~/plugins/contentful.js';

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
        { category: 'street', src: 'top_street.jpg' },
        { category: 'portrait', src: 'top_portrait.jpg' },
        { category: 'landscape', src: 'top_landscape.jpg' },
        { category: 'cycling', src: 'top_cycling.jpg' },
        { category: 'live', src: 'top_live.jpg' },
        { category: 'stilllife', src: 'top_stilllife.jpg' }
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
.vwmax {
  height: 100vh;
  width: 500vw;
  position: relative;
}
.vwmax img.backimg {
  height: 100vh;
  width: auto;
  position: absolute;
  top: 50%;
  left: 10%;
  transform: translate(-50%, -50%);
}

.vwmax img.logoimg {
  height: auto;
  width: 13%;
  position: absolute;
  top: 80%;
  left: 7%;
  transform: translate(-50%, -50%);
}
</style>
