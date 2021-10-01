<template>
  <div>
    <!-- HEADER CONTAINER -->
    <div v-b-toggle.sidebar-no-header class="p-3">
      <!-- moon orbiting -->
      <img
        class="logo"
        src="../assets/frame.svg"
        style="width: 32px; opacity: 0.91"
        alt=""
      />

      <!-- text logo -->
      <img
        class="mx-2"
        src="../assets/bluemoon.svg"
        style="width: 142px; opacity: 0.91"
        alt=""
      />
    </div>

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
          <!-- sidebar title -->
          <h4 id="sidebar-no-header-title" class="my-4">Navigation Menu</h4>

          <!-- sidebar content -->
          <nav class="mb-3">
            <b-nav vertical class="m-4" style="text-align: initial">
              <b-nav-item href="#banner-container" @click="hide"
                >Link</b-nav-item
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

</style>
