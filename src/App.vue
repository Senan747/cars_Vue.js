<script setup>
  import {RouterView, RouterLink} from "vue-router"
</script>
<template>
  <main>
    <div class="links">
      <RouterLink active-class="active" to="/">Home</RouterLink>
      <RouterLink active-class="active" to="/about">About</RouterLink>
    </div>
    <RouterView />
  </main>
</template>

<style scoped>
  .links {
    background-color: #A5B6C7;
    
    padding: 20px;
    text-align: center;
    margin-bottom: 50px;
  }
  .links a {
    color: #ffffff;
    font-size: 25px;
    margin: 0 20px;
    text-decoration: none;
    font-weight: 500;
  }

  .active{
    font-weight: bold;
    
    color: rgb(128, 45, 0);
  }
</style>