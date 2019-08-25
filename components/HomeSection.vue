<template>
  <div class="mt-10">
    <h2 class="is-capitalized is-size-4 mb-5">
      {{ category }}
    </h2>

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
