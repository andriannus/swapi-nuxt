<template>
  <div class="card mt-10">
    <header class="card-header">
      <h2 class="card-header-title is-capitalized is-size-4">
        {{ category }}
      </h2>
    </header>

    <div class="card-content">
      <div class="content">
        <progress
          v-show="isLoading"
          class="progress is-small is-dark"
          max="100"
        >
          15%
        </progress>

        <div class="tags are-medium">
          <span v-for="(resource, index) in resources" :key="index" class="tag">
            {{ resource.name || resource.title }}
          </span>
        </div>
      </div>
    </div>

    <!-- <footer class="card-footer">
      <a class="card-footer-item" href="#">
        More Detail
      </a>
    </footer> -->
  </div>
</template>

<script>
export default {
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
