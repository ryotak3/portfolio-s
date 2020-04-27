<template>
  <section id="myworks" class="section">
    <!-- Title -->
    <div class="section-heading block">
      <h4 class="title is-2">My works</h4>
    </div>
    <b-tabs v-model="activeTab">
      <b-tab-item label="風景">
        <div class="columns is-mobile is-centered">
          <div class="column is-two-thirds">
            <card
              v-for="(post, i) in posts"
              :id="post.sys.id"
              :key="i"
              :title="post.fields.title"
              :date="post.sys.updateAt | moment('YYYY-MM-DD')"
              :imgsrc="post.fields.image.fields.file.url"
            />
          </div>
        </div>
      </b-tab-item>

      <b-tab-item label="ライブ">
        <div class="columns is-mobile is-centered">
          <div class="column is-two-thirds">
            <card
              v-for="(post, i) in posts"
              :id="post.sys.id"
              :key="i"
              :title="post.fields.title"
              :date="post.sys.updateAt | moment('YYYY-MM-DD')"
              :imgsrc="post.fields.image.fields.file.url"
            />
          </div>
        </div>
      </b-tab-item>
      <b-tab-item label="ブライダル">
        <div class="columns is-mobile is-centered">
          <div class="column is-two-thirds">
            <card
              v-for="(post, i) in posts"
              :id="post.sys.id"
              :key="i"
              :title="post.fields.title"
              :date="post.sys.updateAt | moment('YYYY-MM-DD')"
              :imgsrc="post.fields.image.fields.file.url"
            />
          </div>
        </div>
      </b-tab-item>
      <b-tab-item label="ストリートスナップ">
        <div class="columns is-mobile is-centered">
          <div class="column is-two-thirds">
            <card
              v-for="(post, i) in posts"
              :id="post.sys.id"
              :key="i"
              :title="post.fields.title"
              :date="post.sys.updateAt | moment('YYYY-MM-DD')"
              :imgsrc="post.fields.image.fields.file.url"
            />
          </div>
        </div>
      </b-tab-item>
    </b-tabs>
  </section>
</template>

<script>
import moment from 'moment'
import Card from '~/components/Card.vue'
import { createClient } from '~/plugins/contentful.js'

const client = createClient()
export default {
  transition: 'slide-left',
  components: {
    Card
  },
  filters: {
    moment(value, format) {
      return moment(value).format(format)
    }
  },
  asyncData({ env, params }) {
    return client
      .getEntries(env.CTF_BLOG_POST_TYPE_ID)
      .then((entries) => {
        return {
          posts: entries.items
        }
      })
      .catch(console.error)
  }
}
</script>
<style scoped>
.block {
  margin: 2rem;
}
</style>
