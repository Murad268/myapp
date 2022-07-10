<template>
   <button @click="onActive(btn.id)" v-bind:class="(btn.active)?'btn btn-success':'btn btn-warning'">{{btn.name}}</button>
</template>

<script>
   export default {
      props: ["btn", "onActive"]
   }
</script>

<style  scoped>
   button {
      padding: 5px;
      font-weight: 800;
      font-size: 14px;
      color: white;
   }
</style>