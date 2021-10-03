<template>
  <div>
    <!-- HEADER CONTAINER -->
    <div
      v-b-toggle.sidebar-no-header
      class="p-4"
      style="background-color: #0e0e0ed1; position: relative; z-index: 1000"
    >
      <!-- moon orbiting -->
      <img
        class="logo"
        src="../assets/frame.svg"
        style="width: 46px; opacity: 0.91"
        alt=""
      />

      <!-- text logo -->
      <img
        class="mx-2"
        src="../assets/bluemoon.svg"
        style="width: 232px; opacity: 0.91"
        alt=""
      />
    </div>

    <!-- SIDEBAR CONTAINER -->
    <b-sidebar
      id="sidebar-no-header"
      aria-labelledby="sidebar-no-header-title"
      bg-variant="dark"
      text-variant="light"
      no-enforce-focus
      no-header
      shadow
      right
      backdrop
      lazy
    >
      <!-- sidebar structure -->
      <template #default="{ hide }">
        <div class="p-3">
          <!-- sidebar title -->
          <h4 id="sidebar-no-header-title" class="my-4">Navigation Menu</h4>

          <!-- sidebar content -->
          <nav class="mb-3">
            <b-nav vertical class="m-4" style="text-align: initial">
              <b-nav-item href="#section-home" @click="hide">Inicio</b-nav-item>

              <b-nav-item href="#section-gallery" @click="hide">Galeria</b-nav-item>

              <b-nav-item href="#section-product" @click="hide">Produto</b-nav-item>

              <b-nav-item href="#section-highlights" @click="hide">Destaques</b-nav-item>

              <b-nav-item href="#section-form" @click="hide">Formulário</b-nav-item>
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
</style>
