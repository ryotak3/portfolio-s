<template>
  <div>
    <b-navbar class="is-link is-fixed-top">
      <template slot="brand">
        <b-navbar-item tag="router-link" :to="{ path: '/' }">
          <p>weekendcycler</p>
        </b-navbar-item>
      </template>
      <template slot="end">
        <b-navbar-item href="/">PHOTOGRAPHY</b-navbar-item>
        <b-navbar-item href="http://weekendcycler.hateblo.jp/"
          >BLOG</b-navbar-item
        >
        <b-navbar-item href="https://weekenders.fm/">PODCAST</b-navbar-item>
        <b-navbar-item href="/">BIOGRAPHY</b-navbar-item>
        <b-navbar-item href="/about">ABOUT</b-navbar-item>
        <b-navbar-item href="/about">CONTACT</b-navbar-item>
      </template>
    </b-navbar>

    <section class="columns">
      <div class="container column is-12">
        <nuxt />
      </div>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      items: [
        {
          title: 'Home',
          icon: 'home',
          to: { name: 'index' }
        },
        {
          title: 'Inspire',
          icon: 'lightbulb',
          to: { name: 'inspire' }
        }
      ]
    };
  }
};
</script>
