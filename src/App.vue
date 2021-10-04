<template>
  <div id="app">
    <side-bar />

    <router-view />

    <!-- Footer -->
    <footer
      id="section-footer"
      class="text-center text-lg-start bg-light text-muted"
    >
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
          >
            <b-icon
              icon="instagram"
              font-scale="3"
              class="icon-contact"
            ></b-icon>
          </a>

          <a href="https://github.com/ManuelMolina02" class="me-3 text-reset">
            <b-icon icon="github" font-scale="3" class="icon-contact"></b-icon>
          </a>

          <a
            href="https://www.linkedin.com/in/manuel-angel-berger-molina-ba08b3174/"
            class="me-3 text-reset"
          >
            <b-icon
              icon="linkedin"
              font-scale="3"
              class="icon-contact"
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
              <h6 class="text-uppercase fw-bold mb-4">links úteis</h6>
              <p>
                <a href="#!" class="text-reset">Sobre</a>
              </p>
              <p>
                <a href="#!" class="text-reset">Destaque</a>
              </p>
              <p>
                <a href="#!" class="text-reset">Formulário</a>
              </p>
            </div>

            <!-- Contact -->
            <div class="col-md-4 col-lg-3 col-xl-3 mx-auto mb-md-0 mb-4">
              <h6 class="text-uppercase fw-bold mb-4">Contact</h6>
              <p>Florianópolis, SC, BR</p>
              <p>info@example.com</p>
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
@import url("https://fonts.googleapis.com/css2?family=Audiowide&family=Comfortaa:wght@400;500;700&family=Orbitron:wght@400;500;700;900&family=Quantico:wght@400;700&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Oxygen:wght@300;400&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Raleway:wght@200;300;400&display=swap");
#app {
  font-family: "Orbitron", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background-color: #0e0e0e;
}

:root {
  --light-blue: #41b2f1;
  --dark-blue: #2f558c;
  --white: #eeeeeeec;
  --text-white: #dae8f5
}

/* textos e fontes */
.banner-content h1,
.product-content h1,
.highlights-content h1 {
  font-size: 4.8rem;
  font-weight: bold;
  text-align: initial;
}

.banner-content p,
.product-content p,
.highlights-content p,
.form-container p {
  font-family: "Raleway", sans-serif;
  letter-spacing: 1.6px;
  font-size: 32px;
  color: var(--text-white);
  text-align: initial;
}

.product-content span {
  font-size: 22px;
  color: #95a6be;
}

/* botões */

html {
  max-width: 100%;
  overflow-x: hidden;
}

/* scrollbar */
::-webkit-scrollbar {
  width: 10px;
}

::-webkit-scrollbar-track {
  background: #bdbdbd;
}

::-webkit-scrollbar-thumb {
  background: rgb(90, 90, 90);
}

::-webkit-scrollbar-thumb:hover {
  background: rgb(61, 61, 61);
}

/* LOGO ANIMATION */

.logo {
  position: relative;
  z-index: 100;
  display: flex;
  justify-content: center;
  width: 100%;
  align-items: center;
  margin: 1.4rem;
}

/* moon animation orbiting */
.moon-image {
  animation: spin 2.6s linear infinite;
}

.icon-contact:hover {
  color: #2f558c;
  transition: linear 0.5s;
}

/* animations */
@keyframes spin {
  to {
    transform: rotate(360deg);
  }
}

@keyframes filter-animation {
  0% {
    filter: hue-rotate(154deg) saturate(2);
  }

  100% {
    filter: hue-rotate(0);
  }
}

/* RESPONSIVE */

/*texts*/
@media screen and (max-width: 1400px) {
  .banner-content h1,
  .product-content h1,
  .highlights-content h1 {
    font-size: 58px;
  }

  .banner-content p,
  .product-content p,
  .highlights-content p,
  .form-container p {
    font-family: "Raleway", sans-serif;
    letter-spacing: 1.6px;
    font-size: 1.6rem;
    color: aliceblue;
    text-align: initial;
  }

  .product-content span {
    font-size: 1.1rem;
  }

}
</style>
