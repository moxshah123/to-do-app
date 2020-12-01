<template>
  <div>
    <h1>Manage Tasks</h1>
    <todolist/>
  </div>
</template>

<script>
import todolist from './components/todolist.vue';
export default {
    name :"App",
    components:{
         todolist
    },
 
};
</script>

<style>
</style>
