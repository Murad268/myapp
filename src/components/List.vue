<template>
   <div class="list">
      <EmplooyerVue :fly="fly" :key="employeer.id" v-for="employeer in employees" :employeer="employeer" :deleteEmployeer="deleteEmployeer"/>
   </div>
</template>

<script>
   import EmplooyerVue from './Emplooyer.vue'
   export default {
      components: {
         EmplooyerVue
      },
      props: ["employees", "deleteEmployeer", "fly"]
   }
</script>

<style scoped>
   .list {
      margin-top: 20px;
      border: 1px solid rgba(0, 0, 0, 0.3);
      border-radius: 5px;
   }
</style>