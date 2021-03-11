<template>
  <section class="blog">
    <div class="blog__heading">
      <h2 class="blog__heading__title">Blog</h2>
    </div>
    <div class="blog__content">
      <div class="blog__posts" v-if="!loading && !error">
        <blog-article v-for="post in posts" v-bind:key="post.id" :post="post" />
      </div>
      <div class="blog__navigation">
        <base-button :is-rounded="true" :onClick="getPreviousPosts">&#171; Anterior</base-button>
        <base-button :is-rounded="true" :onClick="getNextPosts">Próximo &#187;</base-button>
      </div>
    </div>
  </section>
</template>

<script>
import axios from 'axios'

import BlogArticle from './BlogArticle'
import BaseButton from './BaseButton'

export default {
  name: 'BlogSection',
  components: {
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
}

.blog__heading {
  position: absolute;
  left: 0;
  top: -140px;

  width: 49%;

  background: var(--blue);
}

.blog__heading__title {
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

.blog__content {
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
    margin-top: -10px;
  }

  .blog__heading {
    position: initial;
    width: 100%;

    margin-bottom: 30px;
  }

  .blog__heading__title {
    max-width: 100%;
    
    margin: 0;

    font-size: 2.3rem;
    text-align: center;
  }
}

@media (max-width: 576px) {
  .blog__posts {
    grid-template-columns: 1fr;
  }
}
</style>