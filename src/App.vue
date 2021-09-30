<template>
  <div id="app" class='bg-black'>

    <side-bar/>
    <router-view />

    <div class="footer w-100"
    style="
     background: #10C1E0;
     mix-blend-mode: hard-light;
     height: 700px !important;
     ">
      <div class="footer-content d-flex flex-column py-5" >
        <a class="my-1 " href=""> aaaa </a>
        <a class="my-1 " href=""> aaaa </a>
        <a class="my-1 " href=""> aaaa </a>
        <a class="my-1 " href=""> aaaa </a>
      </div>
    </div>
  </div>

</template>

<script>
import SideBar from '@/components/SideBar.vue';

export default {
  name: 'Home',

  components: {
    SideBar,
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;500;600;800&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Quantico:wght@400;700&display=swap');

#app {
  font-family: "Orbitron", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

side-bar{
   display: flex !important;
    align-items: center;
    justify-content: center;
}

/*text globals*/
.banner-content h1,
.highlights-content h1 {
  font-size: 78px;
  font-weight: bold;
  text-align: initial !important;
}

.banner-content p,
.highlights-content p {
  font-size: 38px;
  text-align: initial !important;
}

</style>
