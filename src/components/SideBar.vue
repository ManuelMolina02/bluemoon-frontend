<template>
  <div class="sidebar-container">
    <div class="menu">
      <a @click="toggleMenu">
        <b-icon-list class="btn-menu" />
      </a>
    </div>

    <div class="sidebar-component">
      <transition name="slide-fade">
        <div class="sidebar" v-if="menuActive">
          <div class="links">
            <a href="#home" @click="toggleMenu">Home</a>
            <a href="#gallery" @click="toggleMenu">Galeria</a>
            <a href="#product" @click="toggleMenu">Produto</a>
            <a href="#highlights" @click="toggleMenu">Destaques</a>
            <a href="#form" @click="toggleMenu">Formulário</a>
          </div>

          <div class="footer">
            <!-- <button class="btn btn-secondary w-100" @click="toggleMenu">
              Sair
            </button> -->
          </div>
        </div>
      </transition>

      <transition name="opacity">
        <div class="sidebar-bg" v-if="menuActive" @click="toggleMenu"></div>
      </transition>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Sidebar',
  data() {
    return {
      menuActive: false,
    };
  },
  methods: {
    toggleMenu() {
      this.menuActive = !this.menuActive;
    },
  },
};
</script>

<style>
/* BOTÃO MENU */
.menu {
  margin: 36px;
  position: fixed;
  top: 0;
  right: 0;
  z-index: 5;
}

.btn-menu {
  width: 52px;
  height: 48px;

  cursor: pointer;
  color: #757575c0;
  border: solid 2px #4e4e4e9a;
  border-radius: 8px;
  transition: ease-in-out 0.2s;
}
.btn-menu:hover {
  background-color: rgba(24, 24, 24, 0.938);
  color: #eeeeeeef;
}

/* BACKDROP */
.sidebar-bg {
  position: fixed;
  top: 0;
  left: 0;
  z-index: 10;
  width: 100vw;
  height: 100vh;
  background-color: rgba(0, 0, 0, 0.329);
}

/* SIDEBAR STRUCTURE */
.sidebar {
  z-index: 20;
  position: fixed;
  top: 0;
  right: 0;
  display: flex;
  flex-direction: column;
  justify-content: space-between;

  width: 320px;
  height: 100vh;
  max-width: 100%;
  max-height: 100%;
  padding: 3rem;
  background-color: #212529;
}

.links {
  display: flex;
  flex-direction: column;
  gap: 15px;
}

.sidebar a {
  text-decoration: none;
  font-size: 1rem;
  letter-spacing: 1px;
  color: #007fe4;
  text-align: initial;
}

.sidebar a:hover {
  color: #007de49c;
}

/*TRANSITIONS*/
/* (estado de entrada e saída) -> de onde está indo ou onde está vindo*/
/* irá realizar um transformação em 95% da transação do eixo X do elemento */
.slide-fade-enter,
.slide-fade-leave-to {
  transform: translateX(98%);
}

/* (como vai acontecer) */
.slide-fade-enter-active,
.slide-fade-leave-active {
  transition: all 0.5s ease-in-out;
}

@media screen and (max-width: 380px) {
  .menu {
    margin: 36px 12px;
  }

}
</style>
