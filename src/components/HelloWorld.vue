<template>
<div>
<input :value="this.todo" @input='(e)=>handlechange(e)'/>
<button @click="submitNote">Add Todo</button>
<p>{{this.todo}}</p>
<ul id="todos">
  <div v-for="(todo, index) in this.todos">
    {{todo}}
    <button @click="(index)=>deleteTodo(index)">X</button>
  </div>
</ul>
</div>
</template>

<script>

export default {
 data() {
      return {
        todo: '',
        todos: []
      };
    },
  name: 'HelloWorld',
  props: {
    msg: String,
    name: String

  },
    methods: {
     submitNote() {
     this.todos.unshift(this.todo)
     this.todo= ''
      },
      handlechange(e){
      this.todo=e.target.value 
   
      },
      deleteTodo(i){
        this.todos.splice(i, 1)
      }
    },
  };
</script>

