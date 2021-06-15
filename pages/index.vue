<template>
    <div class="home-page">

      <div class="about">
        <h3> About Myself </h3>
        <p>
          I am Arun Vijay, from Coimbatore. A student of Electronics and Communication at Amrita School of Engineering. I work on Embedded systems and Digital electronics.
          I like working on software on a variety of platforms, and I am looking for job opportunities in the Electronics Engineering sector.
        </p>
      </div>

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
    const about = await $content('work', params.slug)
      .where({tags: 'about'})
      .fetch();
    return {articles, about};
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
