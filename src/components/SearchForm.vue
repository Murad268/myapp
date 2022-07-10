<template>
   <div class="search">
      <form action="" class="form">
         <input v-bind:value ="search" @input="searchE" type="text" placeholder="işçini tap">
      </form>
   </div>
</template>

<script>
   export default {
      props: ["search", "searchE"]
   }
</script>

<style  scoped>
   .form {
      width: 100%;
   }
   .form input {
      width: 100%;
      padding: 8px 0 8px 10px;
      font-weight: 700;
      border-radius: 5px;
      border: none;
      outline: none;
   }
</style>