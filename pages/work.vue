<template>
    <!-- Display articles in separate cards -->
    <div class="articles">
      <div class="article" v-for="article of articles" :key="article">
          <div class="detail">
            <b-card class="cards" :img-src= article.image >
              <b-card-text>
                <nuxt-link :to="{ name: 'slug', params: {slug: article.slug} }"> {{article.title}} </nuxt-link>
                <br>
                {{article.description}}
              </b-card-text>
            </b-card>
          </div>
      </div>
    </div>
</template>

<script>
export default {
  name: "work",
  async asyncData({$content, params}){
    const articles = await $content('work',params.slug)
      .only(['title', 'description', 'slug','image'])
      .sortBy('createdAt', 'asc')
      .where({ tags: 'project'})
      .fetch();
    return {articles};
  }
}
</script>

<style scoped>

.articles{
  display: block;
  margin-bottom: auto;
  height:100%;
}

.cards{
  display: flex;
  max-width: 500px;
  padding: 5%;
  border-radius: 2%;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
}

img{
  margin: auto;
  width: 90%;
  height:auto;
}

.article{
  display: inline-flex;
  padding: 5%;
  vertical-align: top;
  margin-left:auto;
  max-width: 50%;
}

</style>
