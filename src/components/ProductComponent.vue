<template>

  <div class="product-container w-100 d-flex my-5 mx-auto">
  <div id="gohere"></div>
    <div class="product-images w-50 my-5 pb-5">
      <img
        class="w-100"
        style="max-width: 568px"
        alt="product-image"
        :src="missions.url"
      />
    </div>

    <div class="product-content text-white my-5" style="width: 45%">
      <div class="product-item pb-2">
        <div class="w-75 d-flex">
          <h1>+10.000</h1>
          <span>publicações</span>
        </div>

        <p class="py-3">
          O maior acervo digital de fotos e pesquisas astronômicas da América
          Latina.
        </p>
      </div>

      <div class="product-item pb-4">
        <div class="w-75 d-flex">
          <h1>+32.000</h1>
          <span>cadastros realizados</span>
        </div>

        <p class="py-3">
          Faça parte da nossa comunidade apaixonada pelo espaço e participe das
          trocas de conhecimento que ocorrem nos fóruns.
        </p>
      </div>

      <div class="product-item pb-4">
        <div class="w-75 d-flex">
          <h1>+80</h1>
          <span>colaboradores</span>
        </div>

        <p class="py-3">
          Conteúdos atualizados e explicativos fornecidos por uma equipe de
          pesquisadores e redatores que atuam tornando as matérias acessíveis a
          todos os públicos.
        </p>
      </div>

      <div class="product-item pb-4">
        <div class="w-75 d-flex">
          <h1>+22</h1>
          <span>prêmios internacionais</span>
        </div>

        <p class="py-3">
          Reconhecidos amplamente por ser uma plataforma simples e interativa
          que tem como objetivo detalhar a rotina dos nossos astronautas.
        </p>
      </div>

      <div class="product-item pb-4">
        <div class="w-75 d-flex">
          <h1>+16</h1>
          <span>países</span>
        </div>

        <p class="py-3">
          Tenha acesso exclusivo a materiais escritos em português, inglês e
          espanhol afinal de contas a ciência não tem fronteiras.
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
  color: #007fe4;
  line-height: 0.88;
  margin-bottom: 0 !important;
  padding-right: 0.5rem;
  text-align: initial;
}

.product-content span {
  text-align: left;
  width: min-content;
}

.product-content p {
  width: 65%;
}

.product-images img {
  position: sticky !important;
  border-radius: 8px;
  top: 32px;
  margin-bottom: 1rem !important;

  justify-content: center;
}

@media screen and (max-width: 1500px) {
  .product-content,
  .product-images {
    margin: 3rem;
  }
  .product-content p {
    width: 80%;
  }
}

@media screen and (max-width: 900px) {
  .product-content div {
    flex-direction: column;
    align-items: initial;
  }

  .product-content p {
    width: 100%;
    font-size: 1.3rem;
  }

  .product-content span {
    font-size: 18px;
  }
}

@media screen and (max-width: 675px) {
  .product-container {
    justify-content: center;
  }

  .product-content {
    width: 80% !important;
  }

  .product-images {
    display: none;
  }
}
</style>
