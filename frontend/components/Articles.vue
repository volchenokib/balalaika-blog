<template>
  <section class="flex">
    <article class="w-1/2 text-left ">
      <img
        :src="api_url + articleList[0].image.url"
        alt="balalaika"
        class="max-h-72"
      />

      <div class="mb-8 uppercase font-bold">
        <span>{{ articleList[0].category.name }}</span>
      </div>

      <h2 class="text-4xl">{{ articleList[0].title }}</h2>
    </article>

    <div class="w-1/2 grid grid-cols-2 grid-rows-2 gap-24">
      <template v-for="(article, i) in articleList">
        <article v-if="i > 0" :key="article.id" class="w-1/2">
          <img
            :src="api_url + article.image.url"
            alt="balalaika"
            class="max-h-72"
          />

          <div class="mb-8 uppercase font-bold">
            <span>{{ article.category.name }}</span>
          </div>

          <h2 class="text-4xl">{{ article.title }}</h2>
        </article>
      </template>
    </div>
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
