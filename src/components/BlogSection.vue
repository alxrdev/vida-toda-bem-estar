<template>
  <section class="blog">
    <blog-heading />
    <div class="blog__posts" v-if="!loading && !error">
      <blog-article v-for="post in posts" v-bind:key="post.id" :post="post" />
    </div>
    <div class="blog__navigation">
      <base-button :is-rounded="true" :onClick="getPreviousPosts">&#171; Anterior</base-button>
      <base-button :is-rounded="true" :onClick="getNextPosts">Próximo &#187;</base-button>
    </div>
  </section>
</template>

<script>
import axios from 'axios'

import BlogHeading from './BlogHeading'
import BlogArticle from './BlogArticle'
import BaseButton from './BaseButton'

export default {
  name: 'BlogSection',
  components: {
    BlogHeading,
    BlogArticle,
    BaseButton
  },
  data () {
    return {
      posts: [],
      loading: true,
      error: false,
      page: 1
    }
  },
  created () {
    this.loadPosts(1)
  },
  methods: {
    loadPosts: function (page) {
      axios.get(`https://jsonplaceholder.typicode.com/posts?_page=${page}&_limit=2`)
        .then(response => (this.posts = response.data))
        .catch(() => (this.error = true))
        .finally(() => (this.loading = false))
    },

    getNextPosts: function () {
      const nextPage = this.page+1

      if (nextPage <= (100 / 2)) {
        this.loadPosts(nextPage)
        this.page = nextPage
      }
    },

    getPreviousPosts: function () {
      const previousPage = this.page-1

      if (previousPage >= 1) {
        this.loadPosts(previousPage)
        this.page = previousPage
      }
    }
  }
}
</script>

<style scoped>
.blog {
  position: relative;

  width: 100%;

  margin-top: 90px;
  padding: var(--default-padding);
}

.blog__posts {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 30px;

  width: 100%;
  max-width: 880px;

  margin: 0 auto;
}

.blog__navigation {
  display: flex;
  justify-content: center;
  gap: 10px;
  
  width: 100%;
  
  margin-top: 50px;
}

@media (max-width: 768px) {
  .blog {
    margin-top: 120px;
  }
}

@media (max-width: 576px) {
  .blog__posts {
    grid-template-columns: 1fr;
  }
}
</style>