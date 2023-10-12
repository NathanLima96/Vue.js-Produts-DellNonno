<template>
  <div>
    <b-modal
      hide-backdrop
      centered
      size="lg"
      ref="my-modal"
      id="my-modal"
      hide-footer
      hide-header
      class="m-3"
    >
      <form
        class="p-3"
        ref="form"
        enctype="multipart/form-data"
        @submit.prevent="criarProduto($event)"
      >
        <input
          type="file"
          name="image"
          ref="imageInput"
          @change="handleImageChange"
          class="file mb-3"
          accept="image/*"
        />
        <div class="inputs">
          <b-form-input
            id="name-input"
            v-model="name"
            placeholder="Nome Do Produto"
            required
          >
          </b-form-input>
          <b-form-input
            id="description-input"
            v-model="description"
            placeholder="Descrição Do Produto"
            required
          >
          </b-form-input>
          <b-form-input
            id="value-input"
            v-model="value"
            placeholder="Valor Do Produto"
            required
          >
          </b-form-input>
        </div>
        <div class="button">
          <b-button class="btn-criar" type="submit" @click="hideModal">
            Criar Produto
          </b-button>

          <b-button class="btn-cancelar" type="button" @click="hideModal">
            Cancelar
          </b-button>
        </div>
      </form>
    </b-modal>
  </div>
</template>

<script>
export default {
  name: "mymodal",
  data() {
    return {
      image: "",
      name: "",
      description: "",
      value: "",
    };
  },
  methods: {
    async criarProduto() {
      const formData = new FormData();
      formData.append("name", this.name);
      formData.append("description", this.description);
      formData.append("value", this.value);
      formData.append("image", this.image);

      const req = await fetch("http://localhost:8000/product", {
        method: "POST",
        body: formData,
      });

      const res = await req.json();
    },
    handleImageChange() {
      this.image = this.$refs.imageInput.files[0];
    },
    showModal() {
      this.$refs["my-modal"].show();
    },
    hideModal() {
      this.$refs["my-modal"].hide();
      window.location.reload();
    },
  },
};
</script>

<style scoped>
.inputs {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.button {
  margin-top: 20px;
  display: flex;
  justify-content: center;
  gap: 10px;
}
.btn-criar {
  color: white;
  background: black;
  border-radius: 5px;
}
.btn-criar:hover {
  color: rgb(248, 150, 3);
  background: black;
}
.btn-cancelar {
  color: white;
  background: black;
  border-radius: 5px;
}
.btn-cancelar:hover {
  color: rgb(248, 150, 3);
  background: black;
}

.file {
  background: black;
  color: white;
}
</style>