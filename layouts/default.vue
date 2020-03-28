<template>
  <div>
    <nav class="navbar">
      <div class="container">
        <div class="navbar-brand">
          <a class="navbar-item" href="/">K's Portfolio</a>
          <a
            class="navbar-burger"
            role="button"
            aria-label="menu"
            aria-expanded="false"
          >
            <span aria-hidden="true"></span>
            <span aria-hidden="true"></span>
            <span aria-hidden="true"></span>
          </a>
        </div>
        <div class="navbar-menu">
          <div class="navbar-end">
            <a class="navbar-item" href="/">
              <span class="icon">
                <b-icon icon="camera"></b-icon>
              </span>
              <span>My works</span>
            </a>
            <a class="navbar-item" href="/about">
              <span class="icon">
                <b-icon icon="information"></b-icon>
              </span>
              <span>About</span>
            </a>
          </div>
        </div>
      </div>
    </nav>
    <!-- <div class="navbar is-inline-flex is-transparent">
      <div class="navbar-brand">
        <a class="navbar-item">
          <img
            src="https://bulma.io/images/bulma-logo.png"
            width="112"
            height="28"
            alt="Bulma"
          />
        </a>
      </div>
      <div class="navbar-menu">
        <div class="navbar-item">
          <div class="control has-icons-left">
            <input
              class="input is-small has-text-centered"
              type="text"
              placeholder="search"
            />
            <span class="icon is-left is-small">
              <i class="material-icons">search</i>
            </span>
          </div>
        </div>
      </div>
      <div class="navbar-item is-flex-touch">
        <a class="navbar-item">
          <i class="far fa-file-alt">explore</i>
        </a>
        <a class="navbar-item">
          <i class="material-icons">favorite_border</i>
        </a>
        <a class="navbar-item">
          <i class="material-icons">person_outline</i>
        </a>
      </div>
    </div> -->
    <section class="main-content columns">
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
    }
  }
}
</script>
