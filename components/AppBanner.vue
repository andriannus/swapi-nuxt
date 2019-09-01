<template>
  <section class="bra-5 has-text-centered hero is-family-secondary is-dark">
    <div class="hero-body">
      <div class="container">
        <h1 class="title">{{ title }}</h1>
        <h2 class="subtitle">{{ subtitle }}</h2>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  props: {
    title: {
      default: '',
      type: String
    },
    subtitle: {
      default: '',
      type: String
    }
  }
}
</script>
