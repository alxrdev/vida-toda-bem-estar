<template>
  <div class="hero-box">
    <h1 class="hero-box__title">
      <span class="hero-box__title--top">Vida toda</span>
      <span class="hero-box__title--bottom">Bem Estar</span>
    </h1>
    <p class="hero-box__text">Soluções completas para viver mais e melhor</p>
    <div class="hero-box__cta">
      <base-link :is-button="true" :is-block="true" size="large"  href="#consultoria">Quero uma consultoria</base-link>
    </div>
  </div>
</template>

<script>
import BaseLink from './BaseLink'

export default {
  name: 'HeroBox',
  components: {
    BaseLink
  }
}
</script>

<style scoped>
.hero-box {
  width: 100%;
  height: fit-content;

  padding: 1.5rem var(--default-padding);

  border: 3px solid var(--blue);
}

.hero-box__title {
  margin: 30px 0;
}

.hero-box__title .hero-box__title--top {
  display: block;

  margin-bottom: -5px;

  font-size: 1.95rem;
  font-weight: 500;
  line-height: 100%;
}

.hero-box__title .hero-box__title--bottom {
  font-size: 5.6rem;
  font-weight: 800;
  line-height: 1.1;
  text-transform: uppercase;
}

.hero-box__text {
  display: block;

  margin-top: 100px;
  margin-bottom: 85px;

  font-size: 1.4rem;
}

.hero-box__cta {
  margin: 30px 0;
}

@media (max-width: 960px) {
  .hero-box__title .hero-box__title--top {
    font-size: 1.4rem;
  }

  .hero-box__title .hero-box__title--bottom {
    font-size: 4rem;
  }
}

@media (max-width: 768px) {
  .hero-box {
    max-width: 320px;
  }
  
  .hero-box__title .hero-box__title--top {
    font-size: 1.25rem;
  }

  .hero-box__title .hero-box__title--bottom {
    font-size: 3.6rem;
  }
}

@media (max-width: 310px) {
  .hero-box__text {
    font-size: 1.2rem;
  }

  .hero-box__title .hero-box__title--top {
    font-size: 1rem;
  }

  .hero-box__title .hero-box__title--bottom {
    font-size: 3rem;
  }
}
</style>
