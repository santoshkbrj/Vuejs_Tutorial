<template>
    <div>
        <h3>Computed component</h3>
        <div>Employees present:{{ isEmployeesPresent }}</div>
    </div>
</template>
<script setup>
import { computed, reactive } from 'vue';

    const employees = reactive(['emp1', 'emp2']);
    const isEmployeesPresent = computed(()=>{
     return employees.length>0 ? 'Yes' : 'No'   
     })

</script>
<style>
    
</style>