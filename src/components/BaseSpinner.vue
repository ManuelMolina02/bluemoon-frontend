<template>
  <div>
    <transition name="opacity">
      <div class="base-spinner" v-if="visible">
        <img class="logo" src="../assets/frame1.svg" alt="base-spinner" />

          <img class="text-logo" src="../assets/bluemoon1.svg" alt="base-spinner" />

      </div>
    </transition>
  </div>
</template>

<script>
export default {
  name: 'BaseSpinner',

  data() {
    return {
      visible: true,
    };
  },

  created() {
    this.$root.$on('Spinner::show', () => {
      this.visible = true;
    });
    this.$root.$on('Spinner::hide', () => {
      this.visible = false;
    });
  },
};
</script>

<style scoped>
.base-spinner {
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;

  width: 100%;
  height: 100%;
  position: fixed;
  z-index: 1000;

  display: flex;
  align-items: center;
  justify-content: center;

  background-color: #c9d5eb;
}

.text-logo{
  animation: slide 2s ease-out;
}

.logo {
  width: 100px !important;
  animation: spin 2s linear infinite;
  opacity: 0.8;
}

.opacity-leave-to {
  transform: translateY(-100%);
  opacity: 0;
}

/* (como vai acontecer) */

.opacity-leave-active {
  transition: all 1s ease-in-out;
}

@media screen and (max-width: 500px) {
.base-spinner {
    display: flex;
    flex-direction: column;
}

.logo{
  width: 160px !important;
}
.text-logo{
  width: 70%;
}

}

@keyframes slide {
  0% {
    opacity: 0;
    transform: translateX(100px);
  }
  100% {
        opacity: 1;
        transform: translateX(0);

  }
}

</style>
