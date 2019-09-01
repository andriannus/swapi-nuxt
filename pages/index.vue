<template>
  <div class="container">
    <AppBanner :title="title" :subtitle="subtitle"></AppBanner>

    <HomeSection
      v-for="(category, index) in categories"
      :key="index"
      :category="category"
    ></HomeSection>
  </div>
</template>

<script>
import AppBanner from '~/components/AppBanner.vue'
import HomeSection from '~/components/HomeSection.vue'
import { CATEGORIES } from '~/assets/const/swapi'

export default {
  components: {
    AppBanner,
    HomeSection
  },

  data() {
    return {
      categories: CATEGORIES,
      subtitle: 'The Star Wars API with Nuxt.js',
      title: 'SWAPI - Nuxt.js'
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
