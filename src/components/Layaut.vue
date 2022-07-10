<template>
   <div class="layaut">
      <HeaderVue :countFly="countFly" :employees="employees"/>
      <FiltersAndSearchVue :setTerm="setTerm" :search="search" :searchE="searchE"/>
      <ListVue :fly="fly" :employees="findE(search, sort(term, employees))" :deleteEmployeer="deleteEmployeer" />
      <AddEmployeer :addEmployeer="addEmployeer" :name="name" :salary="salary" :addName="addName" :addSalary = "addSalary"/>
   </div>
</template>

<script>
import HeaderVue from './Header.vue'
import FiltersAndSearchVue from './FiltersAndSearch.vue'
import AddEmployeer from './AddEmployeer.vue'
import ListVue from './List.vue'

   export default {
      components: {
    HeaderVue,
    FiltersAndSearchVue,
    ListVue,
    AddEmployeer
},
      data() {
         return {
            employees: [
               {id: 1, name: "Murad Agamedov", salary: 5000, fly: true},
               {id: 2, name: "Eduard Agamedov", salary: 9000, fly: false},
               {id: 3, name: "Renat Agamedov", salary: 7000, fly: false},
               {id: 4, name: "Anay Qafarova", salary: 600, fly: false},
               {id: 5, name: "Suat Asadov", salary: 800, fly: false},
            ],
            name: "",
            salary: "",
            term: "all",
            search: ""
         }
      },
      methods: {
         deleteEmployeer(id) {
            return this.employees = this.employees.filter(employeer => employeer.id !== id)
         },
         addName(e) {
            this.name = e.target.value
         },
         addSalary(e) {
            this.salary = e.target.value
         },
         addEmployeer() {
            const newEmployeer = {
               id: new Date(),
               name: this.name,
               salary: this.salary
            }
            return this.employees.push(newEmployeer)
         },
         fly(id) {
        
            return this.employees = this.employees.map(employeer => {
                 if(employeer.id == id) {
                  return {...employeer, fly: !employeer.fly}
                 }
                  return employeer
               
            })
         },
         countFly() {
            let count = 0;
            this.employees.forEach(employeer => {
               employeer.fly? count += 1:count += 0
            })
            return count;
         },
         sort(filter, items) {
            switch(filter) {
               case "all":
                  return this.employees = items
               case "flyed":
                  return items.filter(item => item.fly)
               case "more":
                  return items.filter(item => item.salary > 1000)
            }
         },
         setTerm(term) {
            this.term = term
         },
         searchE(e) {
            this.search = e.target.value
         },
         findE(find, items) {
            return items.filter(item => {
               return item.name.includes(find);
            });
         }
      }
   }
</script>

<style  scoped>
   .layaut {
      width: 60%;
      margin: 0 auto;
      margin-bottom: 50px;
   }
</style>