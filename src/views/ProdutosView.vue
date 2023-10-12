<template>
  <div>
    <navbar />
    <div class="container-produto">
      <div v-for="product in products" :key="product.id">
        <div class="">
          <div class="bloco" @click="funcao(product); $bvModal.show('produto-modal')">
            <div class="bloco-imagem" >
              <img class="imagem" :src="'http://localhost:8000/' + product.image" alt="Imagem do Produto">
            </div>
            <div class="bloco-text">
              <p class="nome">{{ product.name }}</p>
              <p>{{ product.description }}</p>
              <p class="valor">R${{ product.value }}</p>
            </div>
          </div>
        </div>
      </div>
      <div class="bloco-criar">
        <div class="button" @click="$bvModal.show('my-modal')">
          <img class="img-criar" src="img/Vectorcriarbranco.svg" alt="">
          <button class="btn-criar" >Criar Produto</button>
        </div>
      </div>
    </div>
    <rodape />
    <modalVue />
    <modalproduto :products="produtos"/>
  </div>
</template>
<script>
import navbar from "@/components/navbar.vue";
import rodape from "@/components/rodape.vue";
import modalVue from "@/components/modal.vue";
import modalproduto from '@/components/modalproduto.vue';

export default {
  name: "Produtos",
  components: {
    navbar,
    rodape,
    modalVue,
    modalproduto,
  },
  data() {
    return {
      products: [],
      produtos:{},
    };
  },
  
  methods: {
    async getProdutos() {
      const req = await fetch("http://localhost:8000/product");
      const data = await req.json();
      this.products = data;
    },
    funcao(product) {
    this.produtos = product;
    console.log(this.produtos);
  },
  },
  mounted() {
    this.getProdutos();
  },
};
</script>

<style scoped>
.container-produto {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  margin: 0px 20px;
  background: #f7f7f7;
  min-height: 80vh;
}
.bloco {
  display: flex;
  flex-direction: column;
  width: 300px;
  height: 400px;
  border: 1px solid rgb(245, 171, 61);
  border-radius: 6px;
  text-align: center;
  align-items: center;
  margin: 20px;
}

.bloco:hover{
  background: white;
  transition: 0.5s;
  cursor: pointer;
}

.bloco-text {
  display: flex;
  flex-direction: column;
}
.bloco-text p {
  margin: 0px;
  padding: 5px;
  margin: 0px auto;
}

.nome {
  color: black;
  font-size: 20px;
  font-family: Arial, Helvetica, sans-serif;
}
.valor {
  font-size: 20px;
  background: rgb(248, 150, 3);
  width: 100px;
  border-radius: 7px;
}
.imagem {
  width: 250px;
  height: 250px;
  padding: 20px;
  border-radius: 30px;
}

.bloco-criar {
  display: flex;
  width: 300px;
  height: 400px;
  text-align: center;
  align-items: center;
  margin: 20px;
  background: white;
}

.button{
  margin: 0px auto;
  display: flex;
  flex-direction: column;
  align-items: center;
  
}
.btn-criar{
  background: none;
  border: none;
  margin: 10px;
  font-size: 20px;
  font-family: Arial, Helvetica, sans-serif;
}

.img-criar{
  width: 30px;
  height: 30px;
  cursor: pointer;
}

@media (max-width:1470px){
  .container-produto {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
}
}
</style>