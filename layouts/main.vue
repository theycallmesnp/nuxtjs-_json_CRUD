<template>
  <div class="header">
    <div class="logo">
      <nav><NuxtLink to="/">LOGO</NuxtLink></nav>
    </div>
    <div class="links">
      <nav><NuxtLink to="/">Home</NuxtLink></nav>
      <NuxtLink to="/about">About</NuxtLink>
      <NuxtLink to="/contact">Contact</NuxtLink>
    </div>
  </div>
  <div>
    <slot />
  </div>
</template>


<script setup>
</script>

<style scoped>
.header {
  background-color:antiquewhite;
  display: flex;
  flex-wrap: nowrap;
  align-content: center;
  justify-content: space-around;
  font-size: 33px;
  
}
.links {
  display: flex;
  column-gap: 90px;

}
.links nav{
    text-decoration: none;
    
}
</style>