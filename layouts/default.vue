<template>
  <div>
    <b-navbar class="is-primary is-fixed-top" transparent="true">
      <template slot="brand">
        <b-navbar-item tag="router-link" :to="{ path: '/' }" class="logo">
          <img class="logoimg" src="~assets/weekendcycler_logo_min.png" alt="weekendcycler" />
        </b-navbar-item>
      </template>
      <template slot="end">
        <b-navbar-dropdown label="PHOTOGRAPHY">
          <b-navbar-item href="/photography?v=portrait">portrait</b-navbar-item>
          <b-navbar-item href="/photography?v=street">street</b-navbar-item>
          <b-navbar-item href="/photography?v=landscape">landscape</b-navbar-item>
          <b-navbar-item href="/photography?v=cycling">cycling</b-navbar-item>
          <b-navbar-item href="/photography?v=live">live</b-navbar-item>
          <b-navbar-item href="/photography?v=stilllife">still life</b-navbar-item>
        </b-navbar-dropdown>
        <b-navbar-item href="http://weekendcycler.hateblo.jp/">BLOG</b-navbar-item>
        <b-navbar-item href="https://weekenders.fm/">PODCAST</b-navbar-item>
        <b-navbar-item href="/biography">BIOGRAPHY</b-navbar-item>
        <b-navbar-item href="/about">ABOUT</b-navbar-item>
        <b-navbar-item href="mailto:weekendcycler1015@gmail.com">CONTACT</b-navbar-item>
        <b-navbar-item href="https://twitter.com/weekendcycler">
          <b-icon icon="twitter" size="is-small"></b-icon>
        </b-navbar-item>
        <b-navbar-item href="https://www.instagram.com/weekendcycler1015/">
          <b-icon icon="instagram" size="is-small"></b-icon>
        </b-navbar-item>
        <b-navbar-item href="https://www.flickr.com/photos/106693263@N04/">
          <b-icon icon="image" size="is-small"></b-icon>
        </b-navbar-item>
        <b-navbar-item href="https://500px.com/weekendcycler1015/">
          <b-icon icon="numeric-5-box" size="is-small"></b-icon>
        </b-navbar-item>
      </template>
    </b-navbar>
    <nuxt />
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
  font-size: 1rem;
}

body {
  color: #ffffff;
}

p {
  font-family: 'Avenir', 'Corbel', '游明朝', 'YuMincho',
    'Hiragino Mincho ProN W3', 'ヒラギノ明朝 ProN W3';
}
span {
  color: #ffffff;
}
nav.navbar.is-fixed-top {
  background: transparent;
}
img.logoimg {
  height: 38px;
  width: 132px;
  min-height: unset;
  max-height: unset;
}
</style>
