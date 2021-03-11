<template>
  <div class="blog-heading">
    <h2 class="blog-heading__title">Blog</h2>
  </div>
</template>

<script>
export default {
  name: 'BlogHeading'
}
</script>

<style scoped>
.blog-heading {
  position: absolute;
  left: 0;
  top: -140px;

  width: 49%;

  background: var(--blue);
}

.blog-heading .blog-heading__title {
  width: 100%;
  max-width: 480px;

  margin: 0;
  margin-left: auto;
  padding: var(--default-padding);

  color: var(--white);

  font-size: 2.8rem;
  font-weight: 500;
  text-align: center;
}

@media (max-width: 768px) {
  .blog-heading {
    position: absolute;
    width: 100%;
    margin-top: 30px;
  }

  .blog-heading .blog-heading__title {
    margin-right: auto;
    font-size: 2.3rem;
  }
}
</style>
