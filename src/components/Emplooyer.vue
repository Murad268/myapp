<template>
   <div @click="fly(employeer.id)" v-bind:class="(!employeer.fly)?'emplooyer':'emplooyer emplooyer__active'">
      <div class="name">{{employeer.name}}</div>
      <div class="salary">{{employeer.salary}}$</div>
      <div @click="deleteEmployeer(employeer.id)" class="delete"><img src="../assets/icons/trash.svg" alt=""></div>
   </div>
</template>

<script>
   export default {
      props: ["deleteEmployeer", "employeer", "fly"]
   }
</script>

<style scoped>
   .delete {
      width: 30px;
      height: 30px;
      cursor: pointer;
   }
   img {
      width: 100%;
      height: 100%;
      object-fit: cover;
   }
   .emplooyer {
      display: grid;
      grid-template-columns: 8fr 3fr 2fr;
      padding: 20px;
      border-bottom: 1px solid black;
      cursor: pointer;
      position: relative;
   }
   .emplooyer__active::after {
      content: "⭐";
      font-size: 40px;
      position: absolute;
      top: 0;
      right: 5px;
   }
   .name, .salary {
      font-weight: 700;
      font-size: 20px;
   }
</style>