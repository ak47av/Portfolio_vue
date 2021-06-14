<template>
  <div>
    <div class="home-page">
      <h1>
        Latest posts
      </h1>

      <!-- Display articles in separate cards -->
      <div class="articles">
        <div class="article" v-for="article of articles" :key="article">
          <nuxt-link :to="{ name: 'slug', params: {slug: article.slug} }">
            <div class="detail">
              <h2> {{article.title}}</h2>
              <h2> {{article.description}}</h2>
            </div>
          </nuxt-link>
        </div>
      </div>



    </div>
  </div>
</template>

<script>
export default {
  async asyncData({$content, params}){
    const articles = await $content('blog',params.slug)
      .only(['title', 'description', 'slug'])
      .sortBy('createdAt', 'asc')
      .fetch();

    return {articles};
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.links {
  padding-top: 15px;
}
</style>
