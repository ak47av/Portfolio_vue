<template>
  <article>
    <h1> Content </h1>
    <nuxt-content :document="article"/>
  </article>
</template>

<script>
export default {
  async asyncData({ $content, params }){
    const article = await $content('blog', params.slug).fetch();

    return {article};
  }
}
</script>

<style scoped>

</style>
