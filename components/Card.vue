<template>
  <div style="margin-top:2rem;">
    <nuxt-link
      :to="{
        name: 'blog-slug',
        params: {
          sys: id
        }
      }"
      class="wrapper"
    >
      <article class="card block">
        <div class="card-image">
          <figure class="image">
            <img :src="imgsrc" />
          </figure>
        </div>
      </article>
    </nuxt-link>
  </div>
</template>
<script>
export default {
  props: {
    title: {
      type: String,
      default: ''
    },
    id: {
      type: String,
      default: ''
    },
    date: {
      type: String,
      default: ''
    },
    imgsrc: {
      type: String,
      default: ''
    }
  }
};
</script>
