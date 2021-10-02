<template>
  <div id="app" class="bg-black">

    <side-bar />

    <router-view />

    <!-- Footer -->
    <footer class="text-center text-lg-start bg-light text-muted">
      <!-- cabeçalho do footer -->
      <div
        class="
          d-flex
          justify-content-center justify-content-lg-between
          p-4
          border-bottom
        "
      >
        <div class="me-5 d-none d-lg-block">
          <span>Connect me on social media:</span>
        </div>

        <div>
          <a
            href="https://www.instagram.com/manuuelmolinaa/"
            class="me-3 text-reset"
          >
            <b-icon icon="instagram" font-scale="3"></b-icon>
          </a>

          <a href="https://github.com/ManuelMolina02" class="me-3 text-reset">
            <b-icon icon="github" font-scale="3"></b-icon>
          </a>

          <a
            href="https://www.linkedin.com/in/manuel-angel-berger-molina-ba08b3174/"
            class="me-3 text-reset"
          >
            <b-icon icon="linkedin" font-scale="3"></b-icon>
          </a>
        </div>
      </div>

      <!-- Section: Links  -->
      <div>
        <div class="container text-center text-md-start mt-5">
          <div class="row mt-3">
            <div class="col-md-3 col-lg-4 col-xl-3 mx-auto mb-4">
              <h6 class="text-uppercase fw-bold mb-4">
                <i class="fas fa-gem"></i>BLUEMOON
              </h6>

              <p>
                This site was developed with the purpose of providing tracking
                of space missions
              </p>
            </div>
            <!-- tecnologias utilizadas -->
            <div class="col-md-2 col-lg-2 col-xl-2 mx-auto mb-4">
              <h6 class="text-uppercase fw-bold mb-4">technologies</h6>
              <p>
                <a href="https://vuejs.org/" class="text-reset">Vue</a>
              </p>
              <p>
                <a href="https://bootstrap-vue.org/" class="text-reset"
                  >Bootstrap-vue</a
                >
              </p>
              <p>
                <a href="https://axios-http.com/" class="text-reset">Axios</a>
              </p>
            </div>

            <div class="col-md-3 col-lg-2 col-xl-2 mx-auto mb-4">
              <h6 class="text-uppercase fw-bold mb-4">Useful links</h6>
              <p>
                <a href="#!" class="text-reset">About</a>
              </p>
              <p>
                <a href="#!" class="text-reset">Highlights</a>
              </p>
              <p>
                <a href="#!" class="text-reset">Form</a>
              </p>
            </div>

            <!-- Contact -->
            <div class="col-md-4 col-lg-3 col-xl-3 mx-auto mb-md-0 mb-4">
              <h6 class="text-uppercase fw-bold mb-4">Contact</h6>
              <p><i class="fas fa-home me-3"></i> Florianópolis, SC, BR</p>
              <p>
                <i class="fas fa-envelope me-3"></i>
                info@example.com
              </p>
              <p><i class="fas fa-phone me-3"></i> (48) 99646-2015</p>
            </div>
          </div>
        </div>
      </div>

      <div
        class="text-center p-4"
        style="background-color: rgba(0, 0, 0, 0.05)"
      >
        © 2021 Developed by Manuel Molina:
      </div>
    </footer>
  </div>
</template>

<script>
import SideBar from '@/components/SideBar.vue';
/*
import BaseSpinner from '@/components/global/BaseSpinner.vue';
*/

export default {
  name: 'Home',

  components: {
    SideBar,
    /* BaseSpinner */
  },
};
</script>

<style>
@import url('./assets/css/style.css');

#app {
  font-family: "Orbitron", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

side-bar {
  display: flex !important;
  align-items: center;
  justify-content: center;
}

/*text globals*/

/* LOGO ANIMATION */

/* moon animation orbiting */
.logo {
  animation: spin 2.6s linear infinite;
}

</style>
