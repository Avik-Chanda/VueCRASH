<template>

    <div class="enclosing" v-bind:class="{'is-complete' : todo.completed}">
      <p class="title">
          <input type="checkbox" v-on:change="markComplete">
          {{todo.title}}
          <button v-on:click="$emit('del-todoItems',todo.id)" class="btn">&times;</button>
          </p>
    </div>

</template>

<script>
export default {
  name: "TodoItems",
  props: ["todo"],
  methods : {
      markComplete()
      {
          this.todo.completed = !this.todo.completed
      }
  }
};
</script>

<style scoped>
.title {
  background-color: azure;
  width: 600px;
  padding: 16px;
  margin:auto;
}
.enclosing {
  margin-top: 20px;;
}
.is-complete
{
    text-decoration : line-through;
}
.btn
{
    float:right;
}
</style>


