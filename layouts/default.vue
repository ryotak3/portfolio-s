<template>
  <div>
    <b-navbar class="is-primary is-fixed-top" transparent="true">
      <template slot="brand">
        <b-navbar-item tag="router-link" :to="{ path: '/' }">
          <p>Weekendcycler</p>
          <!-- <img class="logoimg" src="~assets/weekendcycler_logo_min.png" alt="weekendcycler" /> -->
        </b-navbar-item>
      </template>
      <template slot="end">
        <b-navbar-dropdown label="Photography">
          <b-navbar-item href="/photography?v=portrait">Portrait</b-navbar-item>
          <b-navbar-item href="/photography?v=street">Street</b-navbar-item>
          <b-navbar-item href="/photography?v=landscape">Landscape</b-navbar-item>
          <b-navbar-item href="/photography?v=cycling">Cycling</b-navbar-item>
          <b-navbar-item href="/photography?v=live">Live</b-navbar-item>
          <b-navbar-item href="/photography?v=stilllife">Still Life</b-navbar-item>
        </b-navbar-dropdown>
        <b-navbar-item href="http://weekendcycler.hateblo.jp/">Blog</b-navbar-item>
        <b-navbar-item href="https://weekenders.fm/">Podcast</b-navbar-item>
        <!-- <b-navbar-item href="/biography">Biography</b-navbar-item> -->
        <b-navbar-item href="/about">About</b-navbar-item>
        <b-navbar-item href="mailto:weekendcycler1015@gmail.com">Contact</b-navbar-item>
        <div style="display: flex;">
          <b-navbar-item href="https://twitter.com/weekendcycler">
            <b-icon icon="twitter" size="is-small" class="icon"></b-icon>
          </b-navbar-item>
          <b-navbar-item href="https://www.instagram.com/weekendcycler1015/">
            <b-icon icon="instagram" size="is-small" class="icon"></b-icon>
          </b-navbar-item>
          <b-navbar-item href="https://www.flickr.com/photos/106693263@N04/">
            <b-icon icon="image" size="is-small" class="icon">></b-icon>
          </b-navbar-item>
          <b-navbar-item href="https://500px.com/weekendcycler1015/">
            <b-icon icon="numeric-5-box" size="is-small" class="icon"></b-icon>
          </b-navbar-item>
        </div>
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
  font-family: din-2014, sans-serif;
  font-style: normal;
  font-weight: 400;
}

.text-jp {
  font-family: '游明朝', 'YuMincho', 'Hiragino Mincho ProN W3',
    'ヒラギノ明朝 ProN W3';
}
.text-en {
  font-family: din-2014, sans-serif;
  font-style: normal;
  font-weight: 400;
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
@media (max-width: 767px) {
  .icon {
    color: #666666;
  }
}
</style>
