<template>
  <div class="userdata">
    <p>Name: {{users.name}}</p>
    <p> Email :{{users.email}}</p>
    <p> Phone: {{users.phone}}</p>
   <button> <NuxtLink :to="`/${users.id}`" class="nav">EDIT</NuxtLink></button>
  </div>
</template>
<script setup>

const { users } = defineProps(["users"]); // define the prop
</script>
<style>
.userdata{
   
    font-size: 23px;

    
}
.nav {
    float: left;
    color: aliceblue;
    text-decoration: none;
    font-size: 18px;
    padding: 0 0 0 7px;
}
</style>