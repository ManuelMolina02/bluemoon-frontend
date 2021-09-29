<template>
  <div id="app" class='bg-black'>

    <side-bar/>
    <router-view />
  </div>

</template>

<script>
import SideBar from '@/components/SideBar.vue';

export default {
  name: 'Home',
  data() {
    return {
      registers: [
        {
          title: 'Unwrapped: Five Decade Old Lunar Selfie',
          explanation: "Here is one of the most famous pictures from the Moon -- but digitally reversed. Apollo 11 landed on the moon in 1969 and soon thereafter many pictures were taken, including an iconic picture of Buzz Aldrin taken by Neil Armstrong. The original image captured not only the magnificent desolation of an unfamiliar world, but Armstrong himself reflected in Aldrin's curved visor. Enter modern digital technology. In the featured image, the spherical distortion from Aldrin's helmet has been reversed. The result is the famous picture -- but now featuring Armstrong himself from Aldrin's perspective. Even so, since Armstrong took the picture, the image is effectively a five-decade old lunar selfie. The original visor reflection is shown on the left, while Earth hangs in the lunar sky on the upper right. A foil-wrapped leg of the Eagle lander is prominently visible. Preparations to return humans to the Moon in the next few years include the Artemis program, an international collaboration led by NASA",
          datePublication: '2021 September 27',
          urlImage: 'https://apod.nasa.gov/apod/image/2109/AldrinVisorCrop_Apollo11_1080.jpg',
          urlBigImage: 'https://apod.nasa.gov/apod/image/2109/AldrinVisor_Apollo11_4096.jpg',
        },
      ],
    };
  },
  components: {
    SideBar,
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@200;300;400;600;800&display=swap");
@import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;500;600;800&display=swap');

#app {
  font-family: "Poppins", sans-serif;
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
</style>
