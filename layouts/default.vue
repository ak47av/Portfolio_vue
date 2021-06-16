<template>
  <div class="entire-site">
      <Header/>
    <div class="content">
      <Nuxt/>
    </div>
      <Footer />
    </div>
</template>

<style scoped>

.entire-site{
  margin: auto;
  width: 80%;
  background-color: white;
  position: relative;
  min-height: 100vh;
}

.content{
  padding-bottom: 2.5rem;
}

</style>

<script>
import Header from "../components/Header";
export default {
  components: {Header}
}
</script>
