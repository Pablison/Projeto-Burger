<template>
    <div id="nav">
        <RouterLink to="/">
          <img :src="logo" :alt="logoBurger" id="logo">
        </RouterLink>

        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/pedidos">Pedidos</RouterLink>
    </div>

</template>
<script>
  export default {
    name: "Navbar",
    props:["logo","logoBurger"]
  }
</script>
<style scoped>

</style>

