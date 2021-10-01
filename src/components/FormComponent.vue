<template>
  <div style="background-color: #0e0e0e" class="pb-5">
    <!-- form card -->
    <div
      class="w-50 mx-auto text-white text-start p-5"
      style="border: solid 2px white; border-radius: 4px"
    >
      <b-form @submit="onSubmit" @reset="onReset" v-if="show" class="py-5">
        <div>
          <div class="my-3">
            <div>Value</div>
            <b-form-input
              v-model="text"
              placeholder="Enter your name"
            ></b-form-input>
          </div>

          <div class="my-3">
            <div>Value</div>
            <b-form-input
              v-model="text"
              placeholder="Enter your name"
            ></b-form-input>
          </div>

          <div class="my-3">
            <div>Value</div>
            <b-form-input
              v-model="text"
              placeholder="Enter your name"
            ></b-form-input>
          </div>
        </div>

        <div class="d-flex py-5" style="gap: 15px; justify-content: center">
          <b-button type="submit" variant="primary">Submit</b-button>
          <b-button type="reset" variant="danger">Reset</b-button>
        </div>
      </b-form>
    </div>
  </div>
</template>

<script>
export default {
  name: 'FormComponent',
  data() {
    return {
      form: {
        email: '',
        name: '',
        food: null,
        checked: [],
      },
      show: true,
    };
  },
  methods: {
    onSubmit(event) {
      event.preventDefault();
    },
    onReset(event) {
      event.preventDefault();
      // Reset our form values
      this.form.email = '';
      this.form.name = '';
      this.form.food = null;
      this.form.checked = [];
      // Trick to reset/clear native browser form validation state
      this.show = false;
      this.$nextTick(() => {
        this.show = true;
      });
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
