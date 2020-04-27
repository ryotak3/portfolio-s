<template>
  <div>
    <b-navbar class="is-link is-fixed-top">
      <template slot="brand">
        <b-navbar-item tag="router-link" :to="{ path: '/' }">
          <p>weekendcycler</p>
        </b-navbar-item>
      </template>
      <template slot="end">
        <b-navbar-dropdown label="PHOTOGRAPHY">
          <b-navbar-item href="/photography">portrait</b-navbar-item>
          <b-navbar-item href="/photography">street</b-navbar-item>
          <b-navbar-item href="/photography">landscape</b-navbar-item>
          <b-navbar-item href="/photography">cycling</b-navbar-item>
          <b-navbar-item href="/photography">live</b-navbar-item>
        </b-navbar-dropdown>
        <b-navbar-item href="http://weekendcycler.hateblo.jp/"
          >BLOG</b-navbar-item
        >
        <b-navbar-item href="https://weekenders.fm/">PODCAST</b-navbar-item>
        <b-navbar-item href="/biography">BIOGRAPHY</b-navbar-item>
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
<style lang="scss">
body {
  background-color: #222222;
  color: #ffffff;
}
nav.navbar.is-fixed-top {
  background: transparent;
}
</style>
