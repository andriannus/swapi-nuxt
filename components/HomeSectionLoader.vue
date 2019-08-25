<template>
  <div>
    <ContentLoader :height="23" class="is-hidden-mobile" primaryColor="#4a4a4a">
      <rect x="0" y="0" rx="1.5" ry="1.5" width="50" height="10" />
      <rect x="55" y="0" rx="1.5" ry="1.5" width="75" height="10" />
      <rect x="135" y="0" rx="1.5" ry="1.5" width="65" height="10" />
      <rect x="205" y="0" rx="1.5" ry="1.5" width="30" height="10" />
      <rect x="240" y="0" rx="1.5" ry="1.5" width="100" height="10" />

      <rect x="0" y="12.5" rx="1.5" ry="1.5" width="75" height="10" />
      <rect x="80" y="12.5" rx="1.5" ry="1.5" width="50" height="10" />
    </ContentLoader>

    <ContentLoader
      :height="180"
      class="is-hidden-desktop"
      primaryColor="#4a4a4a"
    >
      <rect x="0" y="0" rx="9" ry="9" width="300" height="50" />
      <rect x="0" y="60" rx="9" ry="9" width="400" height="50" />
      <rect x="0" y="120" rx="9" ry="9" width="200" height="50" />
    </ContentLoader>
  </div>
</template>

<script>
import { ContentLoader } from 'vue-content-loader'

export default {
  components: {
    ContentLoader
  }
}
</script>
