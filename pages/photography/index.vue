<template>
  <section id="myworks" class="section">
    <div class="columns is-mobile is-centered is-multiline">
      <div v-for="(post, i) in posts" :key="i" class="column is-4">
        <card
          v-if="post.fields"
          :id="post.sys.id"
          :key="i"
          :title="post.fields.title"
          :date="post.sys.createdAt | moment('YYYY-MM-DD')"
          :imgsrc="post.fields.image.fields.file.url"
        />
      </div>
    </div>
  </section>
</template>

<script>
import moment from 'moment';
import Card from '~/components/Card.vue';
import { createClient } from '~/plugins/contentful.js';

const client = createClient();
export default {
  transition: 'slide-left',
  components: {
    Card
  },
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
  }
};
</script>
<style scoped>
.block {
  margin: 2rem;
}
</style>
