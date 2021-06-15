<template>
  <header class="header-attributes">

    <b-navbar class="navigation" toggleable="lg">
      <b-navbar-brand href="#">Arun Vijay</b-navbar-brand>

      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav class="ml-auto">            <!--"ml-auto" is to align right -->
          <b-nav-item>
            <nuxt-link to="/"> Home </nuxt-link>
          </b-nav-item>
          <b-nav-item>
            <nuxt-link to="/work"> My Work </nuxt-link>
          </b-nav-item>
          <b-nav-item>
            <nuxt-link to="/skills"> Skills </nuxt-link>
          </b-nav-item>
          <b-nav-item>
            <nuxt-link to="/resume"> Resume </nuxt-link>
          </b-nav-item>
        </b-navbar-nav>
      </b-collapse>



    </b-navbar>
  </header>
</template>

<script>
export default {
  name: "Header"
}
</script>

<style scoped>

.navigation{
  background-color: #ff0000 /*aesthetic ah color podu */
}

.header-attributes {
  height: 100px;
  background-color: #ff0000;
  align-items: center;
}

</style>
