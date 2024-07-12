<template>
    <h1>i am home page</h1>
    <div class="form">
 <input type="text" placeholder="name" v-model="name">

 <input type="text" placeholder="email" v-model="email">
 <input type="text" placeholder="phone" v-model="phone">
 <button @click="submit">Submit</button>
    </div>
</template>

<script setup>
// Define reactive variables for form data
let name = ref('');
let email = ref('');
let phone = ref('');

 async function submit(){
    try{
          const data =  await useFetch('http://localhost:3000/users',{
            method:'POST',
            headers: {
        'Content-Type': 'application/json'
      },
      body: JSON.stringify({
        name: name.value,
        email: email.value,
        phone: phone.value
      })
          })
       
        
  }
  catch(error){
  console.log(error)
  }
   
 }
definePageMeta({
    layout:'main'
})
useHead({
    title:"home page"
})
</script>

<style>
.form{
    row-gap: 23px;
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
    align-content: center;

    
}
.form input {
    height:45px;
    width:50%;
    text-align: center;
    font-size: 27px;
}
button{
    height:45px;
    width:30%;
   margin-left: 181px;
    letter-spacing: 7px;
    font-size: 22px;
    border-radius:23px;
    background-color:green;
    color:white;
}
</style>