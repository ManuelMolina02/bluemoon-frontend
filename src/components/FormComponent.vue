<template>
  <div style="background-color: #0e0e0e" class="my-5 py-5 pb-5">
    <!-- form card -->
    <div
      class="w-50 mx-auto text-white text-start p-5"
      style="border: solid 2px white; border-radius: 4px"
    >
      <form>
        <div class="row mb-4">
          <div class="col">
            <div class="form-outline">
              <label class="form-label" for="form6Example1">Nome</label>
              <input type="text" class="form-control" />
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
          <button type="submit" class="btn btn-primary btn-block btn-lg mb-4">
            enviar
          </button>
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
textarea {
  max-height: 160px;
}
</style>
