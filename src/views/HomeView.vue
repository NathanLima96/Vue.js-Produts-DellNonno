<template>
  <div class="home">
    <navbar />
    <main>
      <!-- Incio main Container Principal-->
      <div class="imagem-backgroud">
        <div class="container">
          <div class="container-text">
            <h1 class="titulo-container">
              Molhos tradicionais <br />
              da Dell Nonno
            </h1>
            <p class="paragrafo">
              A Dell Nonno oferece molhos de tomate tradicionais da mais alta
              qualidade, feitos apenas com os ingredientes mais frescos.
              Aproveite a delícia de nossos molhos em seus pratos favoritos de
              massa, pizza e muito mais!
            </p>
            <a class="botao" href="#">Contato</a>
          </div>
        </div>
      </div>
      <!-- Fim main Container Principal-->

      <!-- Incio main Container-img-->
      
      <div class="container-img">
        <p class="imagem"><carousel/></p>
      </div> 
      <!-- Incio main Container-img

       Incio main Container-Produtos-->
      <div class="container-produtos">
        <div>
          <h1 class="titulo-produto">Produtos</h1>
        </div>
        <div class="produtos">
          <div class="blocos">
            <img src="/img/Molho pizza.jpg" alt="" />
            <div class="text">
              <h2>Molho de Pizza - Dell Nonno</h2>
              <p>
                Seja você um fã de sabores tradicionais ou um aventureiro em
                busca de novas combinações, o molho de pizza é o ingrediente que
                transforma uma simples massa em uma experiência gastronômica
                inesquecível. Preparado com cuidado e paixão, é o segredo que
                faz com que cada fatia seja uma explosão de sabor. Então, pegue
                um pedaço, mergulhe na sedosa combinação de tomates e
                especiarias e deixe-se levar pela magia do molho de pizza.
              </p>
              <router-link to="/produtos" class="botao-produtos"
                >Produtos</router-link
              >
            </div>
          </div>
          <div class="blocos">
            <img src="/img/lanche + ketchup.jpg" alt="" />
            <div class="text">
              <h2>Katchup - Dell Nonno</h2>
              <p>
                Uma das principais características do ketchup é sua
                versatilidade culinária. Seja como condimento para hambúrgueres
                e cachorros-quentes, acompanhamento para batatas fritas
                crocantes, ingrediente em molhos para saladas ou base para
                marinar carnes, o ketchup adiciona um toque especial a qualquer
                refeição. Sua presença nas cozinhas e restaurantes é
                praticamente onipresente, sendo amado por adultos e crianças.
              </p>
              <router-link to="/produtos" class="botao-produtos"
                >Produtos</router-link
              >
            </div>
          </div>
          <div class="blocos">
            <img src="/img/Molho Shoyu.jpg" alt="" />
            <div class="text">
              <h2>Molho Shoyu - Dell Nonno</h2>
              <p>
                Seja usado como um mergulho saboroso, um tempero de marinada ou
                um ingrediente chave em molhos e sopas, o molho shoyu é um
                tesouro culinário que transcende fronteiras. Sua história rica e
                tradição milenar são complementadas por um sabor único e um
                aroma irresistível. Então, embarque nesta jornada culinária e
                permita que o molho shoyu adicione um toque oriental às suas
                criações gastronômicas. Você certamente descobrirá por que o
                molho shoyu é um dos segredos mais saborosos da cozinha mundial.
              </p>
              <router-link to="/produtos" class="botao-produtos"
                >Produtos</router-link
              >
            </div>
          </div>
        </div>
      </div>
      <!-- Fim main Container-Produtos-->

      <!-- Incio main Container-sobre-nos-->
      <div class="container-sobre-nos">
        <div class="text-sobre-nos">
          <h1>Sobre Nós</h1>
          <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Explicabo
            doloribus corporis, repudiandae deserunt nostrum minima
            reprehenderit officia adipisci voluptatibus est neque placeat odio
            veritatis excepturi, sit atque expedita, natus eveniet! Lorem ipsum
            dolor sit, amet consectetur adipisicing elit. Ab, autem placeat,
            culpa sed itaque eaque optio tempore aperiam dolorum voluptates
            fugit amet, error molestias? Autem porro velit obcaecati magni
            molestiae? Lorem, ipsum dolor sit amet consectetur adipisicing elit.
            Qui neque adipisci autem et veniam quaerat ullam possimus molestiae?
            Nulla soluta tempora sapiente magnam expedita quos vero fugit ullam,
            deserunt sint? Lorem ipsum dolor sit amet consectetur adipisicing
            elit. Repellat at beatae earum odit, in nulla, ipsum laboriosam
            maiores, eaque inventore velit? Accusantium reprehenderit id
            corporis facilis debitis fugit velit ipsa? Lorem ipsum dolor sit
            amet, consectetur adipisicing elit. Voluptatum fugiat exercitationem
            natus, consectetur saepe dolores nihil autem quibusdam praesentium
            explicabo, neque nostrum officia pariatur asperiores laboriosam
            omnis nesciunt repudiandae! Quia.
          </p>
        </div>
      </div>
      <!-- Fim main Container-sobre-nos-->
    </main>
    <rodape />
  </div>
</template>

<script>
// @ is an alias to /src
import navbar from "@/components/navbar.vue";
import rodape from "@/components/rodape.vue";
import carousel from "@/components/mycarousel.vue";

export default {
  name: "HomeView",
  components: {
    navbar,
    rodape,
    carousel
  },
};
</script>

<style scoped>
main {
  background-color: rgba(455, 455, 455, 54);
}

.imagem-backgroud {
  height: 80vh;
  color: white;
  width: 98%;
  margin: 10px;
  background: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)),
    url(@/assets/ketchup+maos.jpg);
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
}

.imagem-backgroud + .imagem-backgroud {
  background: linear-gradient(
      rgba(255, 255, 255, 0.5),
      rgba(255, 255, 255, 0.17)
    ),
    url(@/assets/ketchup+maos.jpg);
}

.container-text {
  align-items: center;
  height: 100%;
  width: 80%;
  margin: 0px auto;
  display: flex;
  flex-direction: column;
}

.titulo-container {
  font-family: "Work Sans", sans-serif;
  margin: 140px 50px 40px 50px;
  text-align: center;
  font-size: 4.5em;
  font-weight: 500;
}

.paragrafo {
  margin: 0px 60px;
  font-size: 1.5em;
  text-align: center;
  font-family: "Work Sans", sans-serif;
  font-weight: 400;
}

.botao {
  margin: 30px auto;
  text-decoration: none;
  padding: 12px;
  font-size: 22px;
  font-family: "Open Sans", sans-serif;
  background-color: transparent;
  border: 1px solid rgb(185, 153, 28);
  color: white;
  border-radius: 10px;
  transition: 1s;
}

.botao:hover {
  background-color: rgb(185, 153, 28);
}

/*Fim Main-container*/

/*Inicio main - img*/
.container-img {
  margin: 60px 20px;
  height: 100vh;
  display: flex;
}

.imagem {
  height: 100%;
  width: 95%;
  object-fit: cover;
  object-position: center center;
  margin: 0 auto;
}

/*Fim main - img*/

/*inicio main - produto*/
.container-produtos {
  text-align: center;
  align-items: center;
  display: block;
  margin-top: 150px;
}

.titulo-produto {
  color: rgb(17, 24, 39);
  font-family: "Work Sans", sans-serif;
  font-weight: 500;
  font-size: 48px;
  padding-bottom: 20px;
}

.produtos {
  display: flex;
  justify-content: space-around;
}

.blocos {
  display: flex;
  align-items: center;
  flex-direction: column;
  width: 464px;
  min-height: 688px;
  max-height: 800px;
}

.produtos img {
  width: 463px;
  height: 309px;
  object-fit: cover;
  object-position: center center;
  margin-bottom: 30px;
}

.text {
  text-align: center;
  height: auto;
  display: flex;
  flex-direction: column;
}

.text h2 {
  font-size: 32px;
  color: rgb(17, 24, 39);
  font-family: "Work Sans", sans-serif;
  font-weight: 500;
  margin-bottom: 20px;
}

.text p {
  font-size: 16px;
  color: rgb(17, 24, 39);
  font-family: "Open Sans", sans-serif;
}

.botao-produtos {
  margin: 30px auto;
  text-decoration: none;
  padding: 12px;
  font-size: 15px;
  font-family: "Open Sans", sans-serif;
  background-color: transparent;
  border: 1px solid rgb(185, 153, 28);
  color: rgb(185, 153, 28);
  border-radius: 10px;
  transition: 1s;
}

.botao-produtos:hover {
  background-color: rgb(185, 153, 28);
  color: white;
}

/*Fim main - produto*/

/*Inicio main - Sobre - Nós*/

.container-sobre-nos {
  display: flex;
  text-align: center;
  padding: 40px 24px;
  background-color: #f3f4f6;
  min-height: 300px;
  max-height: 1500px;
  margin-top: 50px;
}

.text-sobre-nos {
  width: 70%;
  margin: auto;
}

.text-sobre-nos h1 {
  font-size: 32px;
  color: rgb(17, 24, 39);
  font-family: "Work Sans", sans-serif;
  font-weight: 500;
  padding-bottom: 30px;
  margin: 0 auto;
}

.text-sobre-nos p {
  font-size: 18px;
  color: rgb(17, 24, 39);
  font-family: "Open Sans", sans-serif;
  margin-bottom: 24px;
}
</style>
