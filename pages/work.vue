<template>
  <div>

    <!-- Display articles in separate cards -->

      <div class="articles">
        <div class="article" v-for="article of articles" :key="article">
          <nuxt-link :to="{ name: 'slug', params: {slug: article.slug} }">
            <div class="detail">
              <b-card v-bind:title="article.title" style="max-width: 20rem;"  class="mb-2" img-src="~/static/lightupdress.png" >
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
  name: "work",
  async asyncData({$content, params}){
    const articles = await $content('work',params.slug)
      .only(['title', 'description', 'slug'])
      .sortBy('createdAt', 'asc')
      .where({ tags: 'project'})
      .fetch();

    return {articles};
  }
}
</script>

<style scoped>

</style>
