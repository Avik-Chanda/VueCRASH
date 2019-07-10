<template>
  <div id="app">
    <Header class="heading" />
    <Add v-on:add-tolist="addtolist"/>
   <Todo v-bind:todos="todos" v-on:del-todo="deleteItems"/>
  </div>
</template>

<script>
import Todo from './components/Todo'
import Header from './components/Layout/Layout'
import Add from './components/AddToList'

export default {
  name: 'app',
  components: {
    Add,
    Header,
    Todo
  },
  data()
  {
    return {
      todos : [
        {
          id: 1,
          title : 'One to do',
          completed : false
        },
        {
          id : 2,
          title : 'Two to do',
          completed : false
        },
        {
          id : 3,
          title : 'Three to do',
          completed : false
        }
      ]
    }
  },
  methods :{
    deleteItems(id)
    {
      this.todos = this.todos.filter(todo => todo.id !== id)
    },
    addtolist(newtodo)
    {
      this.todos = [...this.todos,newtodo]
    }
    
  }
}
</script>

<style >
.heading 
{
  margin : auto;
}
</style>
