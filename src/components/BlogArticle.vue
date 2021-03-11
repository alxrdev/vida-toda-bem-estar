<template>
  <div class="article">
    <div class="article__container">
      <div class="article__header">
        <div class="article__image">
          <base-link href="#"><img src="https://picsum.photos/650" :alt="post.title"></base-link>
        </div>
        <h3 class="article__heading">
          <base-link href="#">{{ post.title }}</base-link>
        </h3>
        <p class="article__text">{{ filterPostDescription }}</p>
      </div>
      <div class="article__footer">
        <base-link :is-button="true" :is-rounded="true" href="#">Continuar</base-link>
      </div>
    </div>
  </div>
</template>

<script>
import BaseLink from './BaseLink'

export default {
  name: 'BlogArticle',
  components: {
    BaseLink
  },
  props: {
    post: {
      type: Object,
      required: true
    }
  },
  computed: {
    filterPostDescription () {
      return `${this.post.body}...`
    }
  }
}
</script>

<style scoped>
.article {
  width: 100%;
}

.article__container {
  position: relative;
  
  display: flex;
  flex-direction: column;
  justify-content: space-between;

  height: 100%;

  border: 3px solid var(--blue);
}

.article__image {
  width: 100%;
  max-height: 250px;

  margin-bottom: 20px;
  contain: content;
}

.article__image img {
  width: 100%;
}

.article__heading {
  margin: 0;
  padding: var(--default-padding);
  padding-bottom: 10px;
}

.article__text {
  padding: var(--default-padding);
  padding-top: 0;
}

.article__footer {
  padding: var(--default-padding);
  padding-bottom: 30px;

  background: var(--blue);
  
  text-align: center;
}

@media (max-width: 768px) {
  .article {
    max-width: 100%;
  }
}
</style>
