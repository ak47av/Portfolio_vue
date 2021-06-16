<template>
  <div>
    <article>
      <nuxt-content :document="article"/>
    </article>
  </div>

</template>

<script>
export default {
  async asyncData({ $content, params }){
    const article = await $content('work',params.slug).fetch();
    return {article};
  }
}
</script>

<style scoped>

</style>
