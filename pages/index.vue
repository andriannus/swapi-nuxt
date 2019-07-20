<template>
  <div class="container">
    <section class="bra-5 has-text-centered hero is-dark">
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
  }
}
</script>
