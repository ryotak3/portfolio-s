<template>
  <section class="index">
    <!-- Title -->
    <div class="section-heading">
      <h4 class="title is-2">My works</h4>
    </div>
    <div class="columns body-columns">
      <div class="column is-half is-offset-one-quarter">
        <card
          v-for="(post, i) in posts"
          :id="post.sys.id"
          :key="i"
          :title="post.fields.title"
          :date="post.sys.updatedAt"
          :imgsrc="post.fields.image.fields.file.url"
        />
      </div>
    </div>
  </section>
</template>

<script>
import Card from '~/components/Card.vue'
import { createClient } from '~/plugins/contentful.js'

const client = createClient()
export default {
  transition: 'slide-left',
  components: {
    Card
  },
  asyncData({ env, params }) {
    return client
      .getEntries(env.CTF_BLOG_POST_TYPE_ID)
      .then((entries) => {
        debugger
        return {
          posts: entries.items
        }
      })
      .catch(console.error)
  }
}
</script>
