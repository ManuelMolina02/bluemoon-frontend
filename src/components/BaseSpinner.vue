<template>
  <div class="base-spinner" v-if="visible">
    <img class="logo" src="../../assets/frame.svg" alt="" />
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

  width: 100vw;
  height: 100vh;
  position: absolute;
  z-index: 1000;

  display: flex;
  align-items: center;
  justify-content: center;

  background-color: rgba(19, 19, 19, 0.849);
}
</style>
