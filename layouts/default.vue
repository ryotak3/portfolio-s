<template>
  <div>
    <b-navbar class="is-primary is-fixed-top" transparent="true">
      <img class="logoimg" src="~assets/weekendcycler_logotype_upperleft.png" alt="weekendcycler" />
      <template slot="brand">
        <b-navbar-item tag="div">
          <a href="/">
            <img
              class="logoimg"
              src="~assets/weekendcycler_logotype_upperleft.png"
              alt="weekendcycler"
            />
          </a>
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
        <b-navbar-item href="http://weekendcycler.hateblo.jp/" target="_blank">Blog</b-navbar-item>
        <b-navbar-item href="https://weekenders.fm/" target="_blank">Podcast</b-navbar-item>
        <!-- <b-navbar-item href="/biography">Biography</b-navbar-item> -->
        <b-navbar-item href="/about">About</b-navbar-item>
        <b-navbar-item href="mailto:weekendcycler1015@gmail.com">Contact</b-navbar-item>
        <div style="display: flex;">
          <b-navbar-item href="https://twitter.com/weekendcycler" target="_blank">
            <b-icon icon="twitter" size="is-small" class="icon"></b-icon>
          </b-navbar-item>
          <b-navbar-item href="https://www.instagram.com/weekendcycler1015/" target="_blank">
            <b-icon icon="instagram" size="is-small" class="icon"></b-icon>
          </b-navbar-item>
          <b-navbar-item href="https://www.flickr.com/photos/106693263@N04/" target="_blank">
            <b-icon icon="image" size="is-small" class="icon">></b-icon>
          </b-navbar-item>
          <b-navbar-item href="https://500px.com/weekendcycler1015/" target="_blank">
            <b-icon icon="numeric-5-box" size="is-small" class="icon"></b-icon>
          </b-navbar-item>
        </div>
      </template>
    </b-navbar>
    <nuxt />
    <footer class="footer">
      <p>Copyright © 2020 Weekendcycler All Rights Reserved.</p>
    </footer>
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
@import url(http://fonts.googleapis.com/earlyaccess/notosansjapanese.css);

html {
  background-color: #222222;
  font-size: 1rem;
}

body {
  color: #ffffff;
  font-family: din-2014, sans-serif;
  font-style: normal;
  font-weight: 400;
  position: relative;
}

.text-jp {
  font-family: 'Noto Sans Japanese', sans-serif;
}
.text-en {
  font-family: din-2014, sans-serif;
  font-style: normal;
  font-weight: 400;
}
.footer {
  position: absolute;
  width: 100%;
  bottom: 0px;
  height: 10px;
  background-color: transparent;
  padding: 30px 0;
  text-align: center;
}
span {
  color: #ffffff;
}
nav.navbar.is-fixed-top {
  background: transparent;
}
.navbar-brand > .navbar-item > .navbar-link.is-active {
  background-color: #ff0000;
}
img.logoimg {
  height: 43px;
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
