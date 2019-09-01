<template>
  <div class="mt-10">
    <div class="level">
      <div class="level-left">
        <div class="level-item">
          <h2 class="is-capitalized is-size-4">
            {{ category }}
          </h2>
        </div>
      </div>

      <div class="level-right">
        <div class="level-item">
          <nuxt-link class="button is-outlined is-dark" :to="`/${category}`">
            <span>Load more</span>

            <span class="icon">
              <i class="fas fa-arrow-right"></i>
            </span>
          </nuxt-link>
        </div>
      </div>
    </div>

    <div class="notification">
      <HomeSectionLoader v-if="isLoading"></HomeSectionLoader>

      <div v-else class="tags are-medium">
        <span
          v-for="(resource, index) in resources"
          :key="index"
          class="tag is-dark is-family-monospace"
        >
          {{ resource.name || resource.title }}
        </span>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.level {
  margin-bottom: 10px;
}
</style>

<script>
import HomeSectionLoader from '~/components/HomeSectionLoader.vue'

export default {
  components: {
    HomeSectionLoader
  },

  props: {
    category: {
      default: '',
      type: String
    }
  },

  data() {
    return {
      resources: [],
      isLoading: false
    }
  },

  mounted() {
    this.getResources()
  },

  methods: {
    getResources() {
      this.isLoading = true

      this.$axios
        .$get(this.category)
        .then(res => {
          this.resources = res.results
        })
        .catch(() => {
          this.resources = []
        })
        .finally(() => {
          this.isLoading = false
        })
    }
  }
}
</script>
