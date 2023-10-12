<template>
  <div>
    <header>
    <router-link to="/" class="logo">Dell Nonno</router-link>
    <nav class="nav-bar">
      <router-link id="nav-item" to="/produtos">Produtos</router-link>
      <a class="icons" target="_blank" href="https://www.instagram.com/dellnonno/"><i
          class="fa-brands fa-instagram"></i></a>
      <a class="icons" target="_blank" href="https://api.whatsapp.com/message/TYIKLPTORVRHG1?autoload=1&app_absent=0"><i
          class="fa-brands fa-whatsapp"></i></a>
      <a class="icons" target="_blank" href="https://www.facebook.com/profile.php?id=100070362006531"><i
          class="fa-brands fa-facebook"></i></a>
    </nav>
  </header>
  </div>
</template>
<script>
export default {
  name: 'navbar',
  
}
</script>

<style scoped>

@import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@300;400;500;600&family=Work+Sans:wght@100;300;400;500;600&display=swap');

header {
   display: flex;
   justify-content: space-between;
   height: 13vh;
   padding: 0 20px;
   align-items: center;
 }

 .nav-bar {
   display: flex;
   gap: 25px;
 }

 .logo {
   font-family: 'Work Sans', sans-serif;
   font-size: 25px;
   font-weight: 600;
   text-decoration: none;
   color: black;
 }

 #nav-item {
   font-family: 'Open Sans', sans-serif;
   font-size: 22px;
   text-decoration: none;
   color: black;
   padding-right: 30px;
   padding: 10px;
 }

 .icons {
   color: black;
   font-size: 25px;
   padding: 10px;
 }

 .icons:hover, #nav-item:hover {
   background-color: rgba(0, 0, 0, 0.1);
   color: black;
   padding: 10px;
   border-radius: 10px;
   transition: 1s;
 }

 .menu-icon {
   background-color: transparent;
   border: none;
   display: none;
 }
</style>