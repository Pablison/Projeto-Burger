<template>
  <Navbar :logo="logo_src" :alt="app_name"/>
  <RouterView />
  <Footer />
</template>

<script >
import Navbar from './components/Navbar.vue';
import Footer from './components/Footer.vue'

export default {
  components:{
    Navbar,
    Footer
  },
  data(){
    return{
      logo_src: "/img/logo.png",
      app_name: "Make your burger"
    }
  }
}
</script>

<style scoped>
  #nav {
    background-color: #222;
    border-bottom: 4px solid #111;
    padding: 15px 50px;
    display: flex;
    justify-content: flex-end;
    align-items: center;
  }
</style>
