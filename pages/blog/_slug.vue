<template>
  <section id="slug" class="section">
    <div class="section-heading">
      <h4 class="title is-2">{{ article.fields.title }}</h4>
    </div>
    <div></div>
    <article class="card block">
      <div class="card-image">
        <figure class="image">
          <img :src="article.fields.image.fields.file.url" />
        </figure>
      </div>
      <div class="card-content">
        <div>{{ article.fields.body.content[0].content[0].value }}</div>
        <p class="slug_date">
          {{ article.sys.updateAt | moment('YYYY-MM-DD') }}
        </p>
      </div>
    </article>
  </section>
</template>
<script>
import moment from 'moment';
import { createClient } from '~/plugins/contentful.js';

const client = createClient();
export default {
  filters: {
    moment(value, format) {
      return moment(value).format(format);
    }
  },
  props: {
    id: {
      type: String,
      default: ''
    }
  },
  transition: 'slide-right',
  async asyncData({ env, params }) {
    return await client
      .getEntry(params.sys)
      .then(entrie => {
        return {
          article: entrie
        };
      })
      .catch(console.error);
  }
};
</script>
