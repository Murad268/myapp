<template>
   <div class="fas bg-primary">
      <SearchFormVue :search="search" :searchE="searchE"/>
      <div  class="btns">
         <Btns @click="setTerm(btn.value)" :onActive="onActive" :key="btn.id" v-for="btn in btns" :btn="btn"/>
      </div>
   </div>
</template>

<script>
import SearchFormVue from './SearchForm.vue'
import Btns from './Btns.vue'
   export default {
      components: {
         SearchFormVue, Btns
      },
      props: ["setTerm", "search", "searchE"],
      data() {
         return {
            btns: [
               {id: 1, name: "hamısı", value: "all", active: true},
               {id: 2, name: "Vəzifəsi qalxacaqlar", value: "flyed", active: false},
               {id: 3, name: "min dollardan çox maaş alanlar", value: "more",  active: false}
            ]
         }
      },
      methods: {
         onActive(id) {
            this.btns = this.btns.map(btn => {
               if(btn.id == id) {
                  return {...btn, active: true}
               } else {
                  return {...btn, active: false}
               }
            })
         }
      }
   }
</script>

<style  scoped>
   .fas {
      padding: 20px;
      margin-top: 30px;
        border-radius: 5px;
   }
   .btns {
      display: flex;
      margin-top: 15px;
      justify-content: space-between;
      width: 62%;
   }
</style>