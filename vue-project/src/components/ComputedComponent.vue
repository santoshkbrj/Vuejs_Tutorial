<template>
    <div>
        <h3>Computed component</h3>
        <div>Employees present:{{ isEmployeesPresent }}</div>
        <div>{{ fullName }}</div>
    </div>
</template>
<script setup>
import { ref, computed, reactive } from 'vue';

    const employees = reactive(['emp1', 'emp2']);
    const isEmployeesPresent = computed(()=>{
     return employees.length>0 ? 'Yes' : 'No'   
     });

     const firstName = ref('Santosh');
     const lastName = ref("Sah");
     const fullName = computed({
       get(){
             return firstName.value + ' ' + lastName.value;
       },
       set(newValue){
         [firstName.value, lastName.value] = newValue.split(' ');
       }
     });
     fullName.value = 'Hi Santosh'

</script>
<style>
    
</style>