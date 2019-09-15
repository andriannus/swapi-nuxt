<template>
  <div class="container">
    <AppBanner :title="title" :subtitle="subtitle"></AppBanner>
  </div>
</template>

<script>
import AppBanner from '~/components/AppBanner.vue'
import { RESOURCES } from '~/assets/const/swapi'
import { capitalize } from '~/utils/transform'

export default {
  components: {
    AppBanner
  },

  data() {
    return {
      title: '',
      subtitle: ''
    }
  },

  mounted() {
    const routeName = this.$route.name
    const selectedResource = this.getSelectedResource(routeName)

    this.setSelectedResource(selectedResource.title, selectedResource.subtitle)
  },

  methods: {
    getSelectedResource(routeName) {
      return RESOURCES.find(resource => {
        return resource.title === capitalize(routeName)
      })
    },

    setSelectedResource(title, subtitle) {
      this.title = title
      this.subtitle = subtitle
    }
  }
}
</script>
