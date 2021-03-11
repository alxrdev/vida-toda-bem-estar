<template>
  <section class="hero">
    <div class="hero__container">
      <div class="hero__container__left">
        <hero-box />
        <hero-text />
      </div>
      <div class="hero__container__right">
        <hero-form />
      </div>
    </div>
  </section>
</template>

<script>
import HeroBox from './HeroBox'
import HeroForm from './HeroForm'
import HeroText from './HeroText'

export default {
  name: 'HeroSection',
  components: {
    HeroBox,
    HeroForm,
    HeroText
  }
}
</script>

<style scoped>
.hero {
  position: relative;
  z-index: 3;

  margin-top: -560px;
}

.hero__container {
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-template-rows: 1fr;
  gap: 60px;

  width: 100%;
  max-width: 880px;
  height: fit-content;

  margin: 0 auto;
}

.hero__container .hero__container__left,
.hero__container .hero__container__right {
  display: flex;
  flex-direction: column;
}

.hero__container .hero__container__left {
  align-items: flex-end;

  margin-top: 80px;
}

.hero__container .hero__container__right {
  align-items: flex-start;

  margin-top: 390px;
}

@media (max-width: 960px) {
  .hero {
    padding: 0 var(--default-padding);
    margin-top: -480px;
  }

  .hero__container .hero__container__right {
    margin-top: 320px;
  }
}

@media (max-width: 768px) {
  .hero__container {
    display: block;
  }

  .hero__container .hero__container__left {
    align-items: center;
  }

  .hero__container .hero__container__right {
    display: none;
  }
}
</style>
