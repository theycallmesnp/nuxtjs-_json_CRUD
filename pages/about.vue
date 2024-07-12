<template>
    <h1> i  am about page</h1>
    <div class="about">
        <div v-for="i in users" :key="i">
            <usersdata :users="i" />
</div>
    </div>
             
</template>

<script setup>
let users=ref([])
const {data} = await useFetch("http://localhost:3000/users",{
    method:'GET',
    headers: {
        'Content-Type': 'application/json'
      },

})
      users.value=data.value
    
definePageMeta({
    layout:'main'
})
useHead({
    title:" about page"
})
</script>

<style>
.about{
    display: flex;
    flex-direction:column;
    -moz-column-gap: 2px;
    column-gap: 2px;
    width: auto;
   
    margin-top: 23px;
    margin-left: 34px;
    justify-content: space-between;
    flex-wrap: wrap;
    align-content: center;
    align-items: stretch;
}
</style>