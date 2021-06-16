<template>
  <header class="header-attributes">

    <b-navbar class="navigation" toggleable="lg">
      <b-navbar-brand>
        <nuxt-link to="/">
          <p style="text-shadow: 1px 1px;color:black; font-size:45px; padding-right: 30rem; font-family: Ubuntu Light" >Arun Vijay</p>
        </nuxt-link>
      </b-navbar-brand>

      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav class="ml-auto">            <!--"ml-auto" is to align right -->
          <b-nav-item>
            <nuxt-link to="/"> <p style="color:black">Home </p></nuxt-link>
          </b-nav-item>
          <b-nav-item>
            <nuxt-link to="/work"><p style="color:black"> My Work</p> </nuxt-link>
          </b-nav-item>
          <b-nav-item>
            <nuxt-link to="/skills"><p style="color:black"> Skills</p> </nuxt-link>
          </b-nav-item>
          <b-nav-item>
            <nuxt-link to="/resume"> <p style="color:black">Resume </p></nuxt-link>
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
.header-attributes{/*aesthetic ah color podu */
  padding: 50px;
}

.navigation{
  display: flex;
  align-items: center;
}
.b-navbar-brand{
  font-size: 1.3rem;
  text-align: center;
}


.header-attributes {
  height: 10%;
  vertical-align: center;
  align-items: center;
  text-align: center;
}
p:hover{
  text-decoration:underline;
  text-decoration-color: rgb(233, 68, 101);
  text-decoration-thickness: 3.5px;

}

</style>
