<template>
    <div class="home-page">

          <!-- Display articles in separate cards -->

          <div class="articles">
            <div class="article" v-for="article of articles" :key="article">
              <nuxt-link :to="{ name: 'slug', params: {slug: article.slug} }">
                <div class="detail">
                  <b-card v-bind:title="article.title" style="max-width: 20rem;"  class="mb-2">
                    <b-card-text>
                      {{article.description}}
                    </b-card-text>
                  </b-card>
                </div>
              </nuxt-link>
            </div>
          </div>

    </div>
</template>

<script>
export default {
  async asyncData({ $content, params}) {
    const articles = await $content('work', params.slug)
      .only(['title', 'description', 'slug'])
      .where({tags: 'skills'})
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
