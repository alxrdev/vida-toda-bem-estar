<template>
  <div class="hero-text">
    <h2 class="hero-text__heading">Pense nisso...</h2>
    <p>
      O quanto o diagnóstico de uma doença grave, internação ou
      cirurgia inesperada pode afetar, hoje, sua vida pessoal e
      financeira?
    </p>
  </div>
</template>

<script>
export default {
  name: 'HeroText'
}
</script>

<style scdoped>
.hero-text {
  width: 100%;
  max-width: 420px;

  margin-top: 40px;
  padding: var(--default-padding);
}

.hero-text__heading {
  margin-bottom: 10px;
}

@media (max-width: 768px) {
  .hero-text {
    max-width: 100%;
    margin-right: auto;
  }
}
</style>
