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
          <img v-lazy="carousel" alt />
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
.vwmax img {
  height: 120vh;
  width: auto;
  position: absolute;
  top: 50%;
  left: 10%;
  transform: translate(-50%, -50%);
}
/* .vwmax {
  height: 100vh;
  width: 500vw;
  margin-left: calc(-1 * ((2000px - 100vw) / 2));
}
.vwmax img {
  height: 120vh;
  width: auto;
  position: relative;
} */
/* .vwmax {
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
} */
</style>
