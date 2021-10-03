<template>
  <div class="product-container w-100 d-flex my-5 mx-auto" >

    <div class="product-images w-50 m-5">
      <img
        class="w-100"
        style="max-width: 568px"
        alt="Banner image"
        :src="missions.url"
      />
    </div>

    <div class="product-content text-white p-2 m-5" style="width: 45%">
      <div class="product-item my-4 py-2">
        <div class="w-75 d-flex">
          <h1>+10.000</h1>
          <span>publicações</span>
        </div>

        <p class="py-3">
          O maior acervo digital de fotos e pesquisas astronômicas da América
          Latina.
        </p>
      </div>

      <div class="product-item my-4 py-2">
        <div class="w-75 d-flex">
          <h1>+32.000</h1>
          <span>cadastros realizados</span>
        </div>

        <p class="py-3">
          Faça parte da nossa comunidade apaixonada pelo espaço e participe das
          trocas de conhecimento que ocorrem nos fóruns.
        </p>
      </div>

      <div class="product-item my-4 py-2">
        <div class="w-75 d-flex">
          <h1>+100</h1>
          <span>colaboradores</span>
        </div>

        <p class="py-3">
          Conteúdos atualizados e explicativos fornecidos por uma equipe de
          pesquisadores e redatores que atuam tornando as matérias acessíveis a
          todos os publicos.
        </p>
      </div>

      <div class="product-item my-4 py-2">
        <div class="w-75 d-flex">
          <h1>+32.000</h1>
          <span>cadastros realizados</span>
        </div>

        <p class="py-3">
          Faça parte da nossa comunidade apaixonada pelo espaço e participe das
          trocas de conhecimento que ocorrem nos fóruns.
        </p>
      </div>

      <div class="product-item my-4 py-2">
        <div class="w-75 d-flex">
          <h1>+32.000</h1>
          <span>cadastros realizados</span>
        </div>

        <p class="py-3">
          Faça parte da nossa comunidade apaixonada pelo espaço e participe das
          trocas de conhecimento que ocorrem nos fóruns.
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ProductComponent',
  data() {
    return {
      missions: {
        copyright: 'CARA Project',
        date: '2021-09-10',
        explanation:
          'Follow every step of the Perseverance and Curiosity robots as they explore the red planet',
        hdurl:
          'https://apod.nasa.gov/apod/image/2109/GalaxySkyMirror_Egon_960.jpg',
        media_type: 'image',
        service_version: 'v1',
        title: 'Missions Mars',
        url: 'https://apod.nasa.gov/apod/image/2109/AuroraIceland_Necchi_1280.jpg',
      },
    };
  },
};
</script>

<style scoped>
/* HIGLIGHTS CONTAINER */
.product-container {
  max-width: 75% !important;
}

.product-content {
  display: flex;
  flex-direction: column;

  align-items: initial;
  justify-content: center;
}

.product-content div {
  align-items: flex-end;
}

.product-content h1 {
  color: var(--light-blue);
  line-height: 0.88;
  margin-bottom: 0 !important;
}

.product-content span {
  text-align: left;
  width: min-content;
}

.product-content p {
  font-size: 28px;
  color: rgb(218, 232, 245);
  font-family: Quantico;

  padding-right: 5rem !important;
}

.product-images img {
  position: sticky !important;
  border-radius: 8px;
  top: 32px;
}

@media screen and (max-width: 1600px) {
  .product-content{
    width: 50% !important;
  }

}
</style>
