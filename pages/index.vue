<template>
  <section id="myworks" class="section">
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
        <span class="image">
          <img :src="carousel.img" />
        </span>
      </b-carousel-item>
    </b-carousel>
  </section>
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
        { img: 'street.jpg' },
        { img: 'portrait.jpg' },
        { img: 'landscape.jpg' },
        { img: 'cycling.jpg' },
        { img: 'live.jpg' }
      ],
      pauseType: 'is-primary',
      interval: 5000,
      animated: 'fade'
    };
  }
};
</script>
<style scoped>
.block {
  margin: 2rem;
}
</style>
