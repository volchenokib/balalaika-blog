<template>
  <section>
    <article>
      <div v-for="article in articleList" :key="article.id">
        <img
          :src="api_url + article.image.url"
          alt="balalaika"
          class="max-h-72"
        />

        <h2>{{ article.title }}</h2>

        <div>
          <span>{{ article.category.name }}</span>
          <span>{{ article.published }}</span>
        </div>

        <div>{{ article.content }}</div>
      </div>
    </article>
  </section>
</template>

<script>
export default {
  props: {
    articles: Array
  },

  data() {
    return {
      api_url: process.env.strapiBaseUri
    };
  },

  computed: {
    articleList() {
      return this.articles;
    }
  }
};
</script>

<style>
.NuxtLogo {
  animation: 1s appear;
  margin: auto;
}

@keyframes appear {
  0% {
    opacity: 0;
  }
}
</style>
