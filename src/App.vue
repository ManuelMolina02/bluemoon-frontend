<template>
  <div id="app">
    <base-spinner/>
    <side-bar />

    <router-view />

    <!-- Footer -->
    <footer id="footer" class="text-center text-lg-start bg-light text-muted">
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
          <span>Me contate através das redes sociais:</span>
        </div>

        <div>
          <a
            href="https://www.instagram.com/manuuelmolinaa/"
            class="me-3 text-reset"
            target="_blank"
          >
            <b-icon
              icon="instagram"
              font-scale="3"
              class="icon-contact"
            ></b-icon>
          </a>

          <a href="https://github.com/ManuelMolina02" class="me-3 text-reset" target="_blank">
            <b-icon icon="github" font-scale="3" class="icon-contact"></b-icon>
          </a>

          <a
            href="https://www.linkedin.com/in/manuel-angel-berger-molina-ba08b3174/"
            class="me-3 text-reset"
            target="_blank"
          >
            <b-icon
              icon="linkedin"
              font-scale="3"
              class="icon-contact"
              target="_blank"
            ></b-icon>
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
                Um site que faz divulgações de fotos e pesquisas do mundo
                intergaláctico!
              </p>
            </div>
            <!-- tecnologias utilizadas -->
            <div class="col-md-2 col-lg-2 col-xl-2 mx-auto mb-4">
              <h6 class="text-uppercase fw-bold mb-4">tecnologias</h6>
              <p>
                <a href="https://vuejs.org/" class="text-reset" target="_blank">Vue</a>
              </p>
              <p>
                <a href="https://bootstrap-vue.org/" class="text-reset" target="_blank"
                  >Bootstrap-vue</a
                >
              </p>
              <p>
                <a href="https://axios-http.com/" class="text-reset" target="_blank">Axios</a>
              </p>
            </div>

            <div class="col-md-3 col-lg-2 col-xl-2 mx-auto mb-4">
              <h6 class="text-uppercase fw-bold mb-4">links</h6>
              <p>
                <a href="#!" class="text-reset">Home</a>
              </p>
              <p>
                <a href="#!" class="text-reset">Produto</a>
              </p>
              <p>
                <a href="#!" class="text-reset">Formulário</a>
              </p>
            </div>

            <!-- Contact -->
            <div class="col-md-4 col-lg-3 col-xl-3 mx-auto mb-md-0 mb-4">
              <h6 class="text-uppercase fw-bold mb-4">Contato</h6>
              <p>Florianópolis, SC, BR</p>
              <p>manuelanmolina@gamil.com</p>
              <p>(48) 99646-2015</p>
            </div>
          </div>
        </div>
      </div>

      <div
        class="text-center p-4"
        style="background-color: rgba(0, 0, 0, 0.05)"
      >
        © 2021 Developed by Manuel Molina
      </div>
    </footer>
  </div>
</template>

<script>
import SideBar from '@/components/SideBar.vue';
import BaseSpinner from '@/components/BaseSpinner.vue';

export default {
  name: 'Home',

  components: {
    SideBar,
    BaseSpinner,
  },

  props: {
    title: String,
  },
  created() {
    console.log(this.title);
  },

  mounted() {
    setTimeout(() => {
      this.$root.$emit('Spinner::hide');
    }, 3000);
  },

};
</script>

<style>
/* LOGO CONFIGS */

.logo {
  position: relative;
  z-index: 3;
  display: flex;
  width: 95vw !important;
  align-items: center;
  margin: 1.4rem;
}

/* moon logo orbiting */
.moon-image {
  animation: spin 3s linear infinite;
}

.icon-contact:hover {
  color: #2f558c;
  transition: linear 0.5s;
}

/* ANIMATIONS */

/* base spinner */
@keyframes spin {
  to {
    transform: rotate(360deg);
  }
}

/* background orbital */
@keyframes zoom {
  0% {
    transform: scale(1) rotate(0);
  }

  50% {
    transform: scale(1.2) rotate(3deg);
  }

  100% {
    transform: scale(1) rotate(0);
  }
}

/* fade text banner */
@keyframes fade-slide-in {
  from {
    opacity: 0;
    transform: translateX(-300px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}
</style>
