<template>
   <div class="header bg-primary">
      <h1 class="company__name">itVektor şirkətinin uçotu</h1>
      <h2 class="allEmployees">Şirkətin ümumi işçilərinin sayı: {{employees.length}}</h2>
      <h3 class="prem">Premiya alaçaqlar: {{countFly()}}</h3>
   </div>
</template>

<script>

   export default {
      props: ["employees", "countFly"]
   }
</script>

<style  scoped>
   .header {
      width: 100%;
      padding: 20px;
      border-radius: 5px;
      margin-top: 30px;
   }
   .company__name, .allEmployees, .prem {
      color: white;
      font-weight: 900;
   }
</style>