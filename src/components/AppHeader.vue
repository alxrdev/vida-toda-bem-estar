<template>
  <div class="header" />
</template>

<script>
export default {
  name: 'AppHeader'
}
</script>

<style scoped>
  .header {
    z-index: 1;

    width: 100%;
    max-width: 100%;
    height: 620px;

    background: url('https://picsum.photos/650') no-repeat;
    background-size: cover;
    background-position: top/center;
  }

  .header::after {
    content: '';
    top: 0;
    bottom: 0;
    right: 0;
    left: 0;

    display: block;

    width: 100%;
    height: 100%;

    background-color: var(--orange);
    filter: opacity(.7);
  }
</style>