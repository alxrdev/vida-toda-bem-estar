<template>
  <div class="home-page">
    <app-header />
    <hero-section />
    <blog-section />
    <consultoria-section />
  </div>
</template>

<script>
import AppHeader from './AppHeader'
import HeroSection from './HeroSection'
import BlogSection from './BlogSection'
import ConsultoriaSection from './ConsultoriaSection'

export default {
  name: 'HomePage',
  components: {
    AppHeader,
    HeroSection,
    BlogSection,
    ConsultoriaSection
  }
}
</script>

<style scoped>
.home-page {
  width: 100%;
}

@media (max-width: 960px) {
  .home-page {
    margin-right: 60px;
  }
}
</style>
