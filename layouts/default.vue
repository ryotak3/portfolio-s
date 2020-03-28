<template>
  <div>
    <b-navbar class="is-link is-fixed-top">
      <template slot="brand">
        <b-navbar-item tag="router-link" :to="{ path: '/' }">
          <p>K's Portfolio</p>
        </b-navbar-item>
      </template>
      <template slot="end">
        <b-navbar-item href="/">
          My works
        </b-navbar-item>
        <b-navbar-item href="/about">
          About
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
    }
  }
}
</script>
