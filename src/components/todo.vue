<template>
<div>
    <li class="d-flex align-items-center list-group-item">
    <button :class="[completed ? 'completed' : 'notCompleted']" @click="$emit('on-toggel')" class="btn border-0 text-left flex-grow-1">{{todoString}}</button>
    <form action="" class="flex-grow-1">
        <input type="text" class="form-control">
    </form>

    <button class="fa fa-pencil btn btn-outline-primary"  ></button>
    <button  key="" @click="$emit('on-delete')" class="fa fa-trash btn btn-outline-danger"></button>

</li>
</div>

  
</template>

<script>

export default {
props:{
    todoString:String,
    completed:Boolean
},
data(){
    return {
        isEditing : false,
        newTodo :""
    }
}
}
</script>

<style scoped>
.notCompleted{
    background-color : darkcyan;
    color: rgb(68, 65, 56);
}

.completed{
    
    text-decoration: line-through;
    color: black;
        background-color: darkgoldenrod;

    
}
</style>
