<template>
  <div>
    <header class="flex flex-row my-4 ml-8">
      <div class="flex-grow">logo</div>
      <nav>
        <ul class="flex flex-row">
          <li
            v-for="category in categories"
            :key="category.id"
            class="mr-8 uppercase"
          >
            <router-link
              class="uk-modal-close"
              :to="{ name: 'categories-id', params: { id: category.id } }"
              tag="a"
              >{{ category.name }}
            </router-link>
          </li>
        </ul>
      </nav>
    </header>
    <main class="mx-8">
      <h1 class="text-6xl mt-32 uppercase">Balalaika Blog</h1>
      <Nuxt />
    </main>
  </div>
</template>

<script>
import categoriesQuery from "~/apollo/queries/category/categories";

export default {
  data() {
    return {
      categories: []
    };
  },
  apollo: {
    categories: {
      prefetch: true,
      query: categoriesQuery
    }
  }
};
</script>

<style>
html {
  font-family: "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI",
    Roboto, "Helvetica Neue", Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}

.button--green {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #3b8070;
  color: #3b8070;
  text-decoration: none;
  padding: 10px 30px;
}

.button--green:hover {
  color: #fff;
  background-color: #3b8070;
}

.button--grey {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #35495e;
  color: #35495e;
  text-decoration: none;
  padding: 10px 30px;
  margin-left: 15px;
}

.button--grey:hover {
  color: #fff;
  background-color: #35495e;
}
</style>
