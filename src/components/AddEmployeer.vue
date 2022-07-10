<template>
   <div class="form bg-primary">
      <h3 class="title">işçi əlavə edin</h3>
      <form @submit.prevent="addEmployeer" action="" >
         <input v-bind:value="name" @input="addName" class="name" type="text" placeholder="ad">
         <input v-bind:value="salary" @input="addSalary" type="number" placeholder="maaş">
         <button>əlavə et</button>
      </form>
   </div>
</template>

<script>
   export default {
      props: ["addName", "addSalary", "name", "salary", "addEmployeer"]
   }
</script>

<style scoped>
   h3 {
      margin-bottom: 15px;
      color: white;
      font-weight: 800;

   }
   .form  {
      padding: 25px;
      margin-top: 30px;
      border-radius: 5px;
   }
   input {
      width: 40%;
      margin-right: 15px;
      height: 35px;
      border-radius: 5px;
      border: none;
      outline: hidden;
      padding-left: 10px;
      font-weight: 800;
   }
   button {
      padding: 5px;
      background: inherit;
      border: 1px solid white;
      color: white;
      font-weight: 800;
      border-radius: 5px;
   }
</style>