<template>
  <div>
    <div class="container">
      <div class="row">
        <div class="col-12"></div>
      </div>
      <div class="row">
        <div class="col-12 col-lg-6">

          <input type="text" v-model="add1" placeholder="Add task">
              <button class="fa fa-plus btn btn-primary" @click="add(add1)"></button>

          <ul class="list-group">
            <todo
              v-for="(todo, i) in todo"
              :key="i"
              :todoString="todo.todoString"
              :completed="todo.completed"
              @on-delete="del(todo)"
              @on-toggel="get(todo)"
              @on-edit="edit(todo, $event)"
            />
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import todo from "./todo";
export default {
  components: {
    todo,
  },
  data() {
    return {
      todo: [
        { todoString: "make videos Angular", completed: true },
        { todoString: "make videos React", completed: false },
        { todoString: "make videos Vue", completed: true },
        { todoString: "make videos JS", completed: false },
      ],
    };
  },

  props: {
    add1 : String
  },

  methods: {
    add(newTodo) {
      this.todo.push({
        todoString: newTodo,
        completed: false,
      });
      this.add1=""
    },

    get(todo) {
      todo.completed = !todo.completed;

    },
    edit(todo, newTodoString) {
      todo.todoString = newTodoString;
    },
    del(deltodo) {
      // this.todo.splice(this.todo.indexOf(deltodo), 1);
     this.todo= this.todo.filter(todos=>{
       return todos.todoString !== deltodo.todoString;
     })
    },
  },
};
</script>

<style>
div {
  background-color: rgb(68, 67, 67);
  color: aliceblue;
}
</style>


























