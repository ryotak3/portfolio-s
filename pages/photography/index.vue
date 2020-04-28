<template>
  <section id="myworks" class="section">
    <div class="columns is-mobile is-centered is-multiline">
      <div v-for="(post, i) in filteredPosts" :key="i" class="column is-4">
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

// const PHOTO_CATEGORY = ['street', 'portrait', 'landscape', 'cycling', 'live'];

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
  },
  data() {
    return {
      categoryId: this.$route.query.v
    };
  },
  computed: {
    filteredPosts() {
      if (!this.categoryId) return this.posts;
      return this.posts.filter(post => {
        if (post.fields.tags) {
          for (const tag of post.fields.tags) {
            if (tag.fields.slug === this.categoryId) {
              return true;
            }
          }
        }
      });
    }
  }
};
</script>
