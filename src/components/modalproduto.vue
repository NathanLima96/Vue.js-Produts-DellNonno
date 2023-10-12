<template>
  <div>
    <b-modal
      hide-backdrop
      centered
      size="lg"
      ref="produto-modal"
      id="produto-modal"
      hide-footer
      hide-header
      class="m-3"
    >
      <div class="container">
        <div class="conteudo">
          <div class="name">
            <p class="name-text" v-if="!preview">{{ products.name }}</p>
            <p v-else>
              <b-form-input
                id="name-input"
                v-model="name"
                placeholder="Nome Do Produto"
              >
              </b-form-input>
            </p>
          </div>
          <div class="description">
            <p class="description-text" v-if="!preview">
              {{ products.description }}
            </p>
            <p v-else>
              <b-form-input
                id="description-input"
                v-model="description"
                placeholder="Descrição Do Produto"
              >
              </b-form-input>
            </p>
          </div>
          <div class="value">
            <p class="value-text" v-if="!preview">R$ {{ products.value }}</p>
            <p v-else>
              <b-form-input
                id="value-input"
                v-model="value"
                placeholder="Valor Do Produto"
              >
              </b-form-input>
            </p>
          </div>
          <div class="container-imagem">
            <p v-if="!preview">
              <img
                class="imagem"
                :src="'http://localhost:8000/' + products.image"
                alt="Imagem do Produto"
              />
            </p>
            <!-- <p v-else>
              <input
                type="file"
                name="image"
                ref="imageInput"
                @change="handleImageChange"
                class="file mb-3"
                accept="image/*"
              />
            </p> -->
          </div>
          <div v-if="!preview"></div>
          <div v-else>
            <b-button class="btn-criar" type="submit" @click="update(products)">
              Editar Produto
            </b-button>
          </div>
        </div>
        <div class="menu-lateral">
          <div class="functions">
            <div class="itens" @click="excluir(products.id)">
              <img src="img/VectorExcluir.svg" alt="" />
              <p class="tag-functions">Excluir</p>
            </div>
          </div>
          <div class="functions">
            <div class="itens" @click="editar()">
              <img class="w-10" src="img/Vectoreditar.svg" alt="" />
              <p class="tag-functions">Editar</p>
            </div>
          </div>
          <div class="functions">
            <div class="itens">
              <img src="img/VectorImprimir.svg" alt="" />
              <p class="tag-functions">Imprimir</p>
            </div>
          </div>
          <div class="functions">
            <div class="itens">
              <img src="img/VectorCopiar.svg" alt="" />
              <p class="tag-functions">Copiar</p>
            </div>
          </div>
        </div>
      </div>
    </b-modal>
  </div>
</template>

<script>
export default {
  name: "modalproduto",
  data() {
    return {
      preview: false,
      name: "",
      value: "",
      description: "",
      image: "",
    };
  },
  props: {
    products: Object,
  },
  methods: {
    editar() {
      this.preview = true;
    },
    async update(products) {
      const editar = await fetch(
        `http://localhost:8000/product/${products.id}`,
        {
          method: "PUT",
          headers: {
            "Content-Type": "application/json",
          },
          body: JSON.stringify({
            name: this.name,
            value: this.value,
            description: this.description,
          }),
        }
      );
      window.location.reload();
    },
    async excluir(productId) {
      const excluir = await fetch(
        `http://localhost:8000/product/${productId}`,
        {
          method: "DELETE",
        }
      );
      window.location.reload();
    },
  },
};
</script>

<style scoped>
.imagem {
  width: 350px;
  height: 350px;
  padding: 20px;
  border-radius: 30px;
}

.container {
  display: flex;
  justify-content: space-between;
}

.conteudo {
  text-align: center;
}

.menu-lateral {
  background: #f7f7f7;
  min-width: 30%;
}

.itens {
  display: flex;
  gap: 13px;
  min-width: 70%;
  margin: 10px;
  cursor: pointer;
  border-radius: 6px;
  padding: 5px 10px;
}

.tag-functions {
  margin-top: 12px;
}

.itens:hover {
  background: #b8b8b8b4;
}

.name-text {
  color: black;
  font-size: 20px;
  font-family: Arial, Helvetica, sans-serif;
}

.value-text {
  font-size: 20px;
  background: rgb(248, 150, 3);
  width: 100px;
  margin: 0 auto;
  border-radius: 7px;
  text-align: center;
}

.container-imagem {
  margin: 0 auto;
}
</style>