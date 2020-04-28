<template>
  <div>
    <b-navbar class="is-primary is-fixed-top">
      <template slot="brand">
        <b-navbar-item tag="router-link" :to="{ path: '/' }">
          <p>weekendcycler</p>
        </b-navbar-item>
      </template>
      <template slot="end">
        <b-navbar-dropdown label="PHOTOGRAPHY">
          <b-navbar-item href="/photography?v=portrait">portrait</b-navbar-item>
          <b-navbar-item href="/photography?v=street">street</b-navbar-item>
          <b-navbar-item href="/photography?v=landscape">
            landscape
          </b-navbar-item>
          <b-navbar-item href="/photography?v=cycling">cycling</b-navbar-item>
          <b-navbar-item href="/photography?v=live">live</b-navbar-item>
        </b-navbar-dropdown>
        <b-navbar-item href="http://weekendcycler.hateblo.jp/">
          BLOG
        </b-navbar-item>
        <b-navbar-item href="https://weekenders.fm/">PODCAST</b-navbar-item>
        <b-navbar-item href="/biography">BIOGRAPHY</b-navbar-item>
        <b-navbar-item href="/about">ABOUT</b-navbar-item>
        <b-navbar-item href="/about">CONTACT</b-navbar-item>
        <b-navbar-item href="https://twitter.com/weekendcycler">
          <i class="fab fa-twitter"></i>
        </b-navbar-item>
        <b-navbar-item href="https://www.instagram.com/weekendcycler1015/">
          <i class="fab fa-instagram"></i>
        </b-navbar-item>
        <b-navbar-item href="https://www.flickr.com/photos/106693263@N04/">
          <i class="fab fa-flickr"></i>
        </b-navbar-item>
        <b-navbar-item href="https://500px.com/weekendcycler1015/">
          <i class="fab fa-500px"></i>
        </b-navbar-item>
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
<style>
html {
  background-color: #222222;
}
nav.navbar.is-fixed-top {
  background: transparent;
}
</style>
