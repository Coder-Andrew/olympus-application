<template>
  <nav>
    <RouterLink :to="{ name: 'home' }">Home</RouterLink> | 
    <RouterLink :to="{ name: 'CRUD' }">CRUD Page</RouterLink>
  </nav>
  <RouterView />
</template>

<script setup>

</script>

<style>
  nav {
    text-align: center;
    margin-bottom: 20px;
  }
  nav a {
    text-decoration: none;
  }
</style>