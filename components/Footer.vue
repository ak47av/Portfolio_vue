<template>
  <footer class="footer-attributes">
    <hr>
      <div class="footer-container">
        <p class="footer-items">
          Mail <br> av.ar.vijay@gmail.com
        </p>

        <p class="footer-items">
          Social <br>
          <a href="https://www.linkedin.com/in/arun-vijay-61248b17a/" target="_blank" rel="noopener noreferrer">Linkedin</a>
          / <a href="https://github.com/ak47av" target="_blank" rel="noopener noreferrer">Github</a>
        </p>

        <p class="footer-items">
          Phone <br>
          +91 8754072188
        </p>

      </div>
  </footer>
</template>

<script>
export default {
  name: "Footer"
}
</script>

<style scoped>

.footer-container{
  display: flex;
  align-items: center;
  justify-content: center;
}

.footer-items{
  padding-right: 10%;
  padding-left: 10%;
}

.footer-attributes {
  width:100%;
  position: absolute;
  bottom:0;
  vertical-align: center;
  clear:both;
  height: 2.5rem;
}
p:hover{
  text-decoration:underline;
  text-decoration-color: rgb(233, 68, 101);
  text-decoration-thickness: 3.5px;

}

</style>
