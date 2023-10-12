<template>
  <div>
    <footer>
    <div class="logo">Dell Nonno</div>
    <div class="nav-footer">
      <router-link id="item-footer" to="/">Home</router-link>
      <router-link id="item-footer" to="/produtos">Produtos</router-link>
      <a class="icons-footer" target="_blank" href="https://www.instagram.com/dellnonno/"><i
          class="fa-brands fa-instagram"></i></a>
      <a class="icons-footer" target="_blank"
        href="https://api.whatsapp.com/message/TYIKLPTORVRHG1?autoload=1&app_absent=0"><i
          class="fa-brands fa-whatsapp"></i></a>
      <a class="icons-footer" target="_blank" href="https://www.facebook.com/profile.php?id=100070362006531"><i
          class="fa-brands fa-facebook"></i></a>
    </div>
  </footer>
  </div>
</template>
<script>
export default {
  name:'rodape',
}
</script>
<style scoped>
footer {
   color: white;
   background-color: #AB150F;
   display: flex;
   justify-content: space-between;
   min-height: 150px;
   max-height: 400px;
   align-items: center;
   padding: 0 20px;
   gap: 20px;
 }
 .logo {
   font-family: 'Work Sans', sans-serif;
   font-size: 25px;
   font-weight: 600;
 }

 .nav-footer {
   display: flex;
 }

 #item-footer {
   font-family: 'Open Sans', sans-serif;
   font-size: 18px;
   text-decoration: none;
   color: white;
   padding-right: 30px;
   padding: 10px;
 }

 .icons-footer {
   color: white;
   font-size: 22px;
   padding: 10px;
 }

 .icons-footer:hover, #item-footer:hover {
   background-color: rgba(0, 0, 0, 0.3);
   padding: 10px;
   border-radius: 10px;
   transition: 1s;
 }
</style>