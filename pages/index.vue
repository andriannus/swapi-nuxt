<template>
  <div class="container">
    <section class="bra-5 has-text-centered hero is-family-secondary is-dark">
      <div class="hero-body">
        <div class="container">
          <h1 class="title">SWAPI - Nuxt.js</h1>
          <h2 class="subtitle">The Star Wars API with Nuxt.js</h2>
        </div>
      </div>
    </section>

    <HomeSection
      v-for="(category, index) in categories"
      :key="index"
      :category="category"
    ></HomeSection>
  </div>
</template>

<script>
import HomeSection from '~/components/HomeSection.vue'
import { SWAPI } from '~/assets/const/swapi'

export default {
  components: {
    HomeSection
  },

  data() {
    return {
      categories: SWAPI.CATEGORIES
    }
  },

  head() {
    return {
      title: 'SWAPI - Nuxt.js',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'The Star Wars API with Nuxt.js'
        },
        {
          hid: 'title',
          name: 'title',
          content: 'SWAPI - Nuxt.js'
        },
        {
          hid: 'og:description',
          property: 'og:description',
          content: 'The Star Wars API with Nuxt.js'
        },
        {
          hid: 'og:title',
          property: 'og:title',
          content: 'SWAPI - Nuxt.js'
        },
        {
          hid: 'og:url',
          name: 'og:url',
          content: 'https://swapi-nuxt.andriannus.id/'
        },
        {
          hid: 'twitter:description',
          name: 'twitter:description',
          content: 'The Star Wars API with Nuxt.js'
        },
        {
          hid: 'twitter:title',
          name: 'twitter:title',
          content: 'SWAPI - Nuxt.js'
        }
      ]
    }
  }
}
</script>
