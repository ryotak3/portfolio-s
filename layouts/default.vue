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
    <!-- sidebar -->
    <!-- <b-sidebar :mobile="mobile" :expand-on-hover="true" :reduce="true" type="is-black" open>
      <div>
        <b-menu class="is-custom-mobile">
          <b-menu-list>
            <b-menu-item tag="router-link" :to="{ path: '/' }" label="weekendcycler"></b-menu-item>
          </b-menu-list>
          <b-menu-list>
            <b-menu-item label="PHOTOGRAPHY">
              <b-menu-item href="/photography?v=portrait" label="portrait"></b-menu-item>
              <b-menu-item href="/photography?v=street" label="street"></b-menu-item>
              <b-menu-item href="/photography?v=landscape" label="landscape"></b-menu-item>
              <b-menu-item href="/photography?v=cycling" label="cycling"></b-menu-item>
              <b-menu-item href="/photography?v=live" label="live"></b-menu-item>
              <b-menu-item href="/photography?v=stilllife" label="still life"></b-menu-item>
            </b-menu-item>
            <b-menu-item href="http://weekendcycler.hateblo.jp/" label="BLOG"></b-menu-item>
            <b-menu-item href="https://weekenders.fm/" label="PODCAST"></b-menu-item>
            <b-menu-item href="/biography" label="BIOGRAPHY"></b-menu-item>
            <b-menu-item href="/about" label="ABOUT"></b-menu-item>
            <b-menu-item href="mailto:xxx@gmail.com" label="CONTACT"></b-menu-item>
          </b-menu-list>
          <b-menu-list>
            <b-menu-item href="https://twitter.com/weekendcycler" icon="twitter"></b-menu-item>
            <b-menu-item href="https://www.instagram.com/weekendcycler1015/" icon="instagram"></b-menu-item>
            <b-menu-item href="https://www.flickr.com/photos/106693263@N04/" icon="image"></b-menu-item>
            <b-menu-item href="https://500px.com/weekendcycler1015/" icon="numeric-5-box"></b-menu-item>
          </b-menu-list>
        </b-menu>
      </div>
    </b-sidebar>-->
    <!-- sidebar -->

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
.b-sidebar .sidebar-content {
  background: transparent;
}
</style>
