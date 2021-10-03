<template>
  <div class="sidebar-container">
    <!-- HEADER CONTAINER -->
    <div id="icon-menu" v-b-toggle.sidebar-no-header class="p-4 mx-2">
      <b-icon-list class="icon-list" />
    </div>

    <!-- tooltip -->

    <!-- SIDEBAR CONTAINER -->
    <b-sidebar
      id="sidebar-no-header"
      aria-labelledby="sidebar-no-header-title"
      bg-variant="dark"
      text-variant="light"
      no-header
      shadow
      right
      backdrop
      lazy
    >
      <!-- sidebar structure -->
      <template #default="{ hide }">
        <div class="p-3">
          <!-- sidebar content -->
          <nav class="mb-3">
            <b-nav vertical class="m-4" style="text-align: initial">
              <b-nav-item class="nav-link" href="#section-home" @click="hide"
                >Inicio</b-nav-item
              >

              <b-nav-item class="nav-link" href="#section-gallery" @click="hide"
                >Galeria</b-nav-item
              >

              <b-nav-item class="nav-link" href="#section-product" @click="hide"
                >Produto</b-nav-item
              >

              <b-nav-item
                class="nav-link"
                href="#section-highlights"
                @click="hide"
                >Destaques</b-nav-item
              >

              <b-nav-item class="nav-link" href="#section-form" @click="hide"
                >Formulário</b-nav-item
              >
            </b-nav>
          </nav>
        </div>
      </template>
    </b-sidebar>
  </div>
</template>

<script>
export default {
  name: 'SideBar',
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.sidebar-container {
  position: fixed;
  z-index: 10000;
  right: 0.75rem;
  top: 0.75rem;
}

.icon-list {
  color: #757575c0;
  border: solid 2px #4e4e4e9a;
  border-radius: 8px;

  width: 52px;
  height: 48px;

  transition: ease-in-out 0.2s;
}

.icon-list:hover {
  background-color: rgba(24, 24, 24, 0.938);
  color: #eeeeeeef;
}

.nav-link {
  color: var(--light-blue);
}
</style>
