<template>
    <h1>I am Edit page</h1>
    <div class="form">
 <input type="text" placeholder="name" v-model="name">

 <input type="text" placeholder="email" v-model="email">
 <input type="text" placeholder="phone" v-model="phone">
 <button @click="edit">Submit</button>
    </div>
</template>
<script  setup>
        const router = useRouter();
        const { id } = useRoute().params;

        
let name= ref('');
let email = ref('');
let phone = ref('');





const {data} = await useFetch(`http://localhost:3000/users/${id}`,{
    method:'GET',
    headers: {
        'Content-Type': 'application/json'
      },
                 
});

    name.value = data.value.name;
    email.value = data.value.email;
    phone.value = data.value.phone;

async function edit(){
    try{
          const { id } = useRoute().params;
          const data =  await useFetch(`http://localhost:3000/users/${id}`,{
            method:'PUT',
            headers: {
        'Content-Type': 'application/json'
      },
      body: JSON.stringify({
        name: name.value,
        email: email.value,
        phone: phone.value
      })
          })
          console.log(data);
        

          router.push({ name: 'about' });
        
  }
    catch(error){
        console.log(error);
    }
}


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
h1{
    text-align: center;
}

</style>