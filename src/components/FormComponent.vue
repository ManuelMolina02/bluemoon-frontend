<template>
  <div style="background-color: #e4eaf5" class="my-5 py-5 pb-5">
    <div class="form-card col-7 mx-auto text-start p-5">
      <form>
        <div class="row mb-4">
          <div class="col">
            <div class="form-outline">
              <label class="form-label">Nome</label>
              <input type="text" class="form-control name-input" />
            </div>
          </div>

          <div class="col">
            <div class="form-outline">
              <label class="form-label">Sobrenome</label>
              <input type="text" class="form-control" />
            </div>
          </div>
        </div>

        <div class="form-outline mb-4">
          <label class="form-label">Endereço</label>
          <input type="text" class="form-control" />
        </div>

        <div class="form-outline mb-4">
          <label class="form-label">E-mail</label>
          <input type="email" class="form-control" />
        </div>

        <div class="form-outline mb-4">
          <label class="form-label">Telefone</label>
          <input type="number" class="form-control" />
        </div>

        <div class="form-outline mb-4">
          <label class="form-label">Informações Adicionais</label>
          <textarea class="form-control" rows="4"></textarea>
        </div>

        <div class="form-check form-switch d-flex justify-content-center mb-4">
          <input class="form-check-input me-2" type="checkbox" checked />

          <label class="form-check-label">
            Li e aceito os termos de uso.
          </label>
        </div>

        <div class="w-100 d-flex justify-content-center">
          <a
            type="submit"
            href="#section-form"
            class="btn btn-primary btn-block btn-lg mb-4"
            style="background-color: #002a68; border: solid 1px #002a68"
          >
            enviar
          </a>
        </div>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: 'FormComponent',
};
</script>

<style scoped>
.form-control {
  height: 60px !important;
}
.form-card {
  border: solid 2px rgb(26 40 69);
  color: rgb(26 40 69);
  border-radius: 4px;
}
.form-check-input:checked {
  background-color: #002a68;
  border-color: #002a68;
}
.form-label {
  margin: 0 !important;
}
textarea {
  max-height: 160px;
}

@media screen and (max-width: 1440px) {
  .form-card {
    width: 75% !important;
  }
}

@media screen and (max-width: 900px) {
  .form-card form div {
    display: flex;
    flex-direction: column;
  }

  .name-input {
    margin-bottom: 1.3rem !important;
  }

  .form-check {
    flex-direction: row !important;
  }
}

@media screen and (max-width: 600px) {
  .form-control {
    height: 80px !important;
  }
  .form-card {
    width: 90% !important;
  }
}
</style>
