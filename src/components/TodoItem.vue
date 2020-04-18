<template>
  <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
    <p>
      <input type="checkbox" @change="markComplete"/>
    {{todo.title}}
    <button class="del" @click="$emit('del-todo', todo.id)" >x</button>
    </p>
  </div>
</template>

<script>
  export default {
    name: "TotoItem",
    
    props: ["todo"],

    methods: {
      markComplete() {
        this.todo.completed = !this.todo.completed
      }
    }
  }

</script>

<style scoped>
  .todo-item {
    background: #f1f1f1;
    padding: 10px;
    border-bottom: 2px #444 dashed;
  }

  .is-complete {
    background: #00dd00;
    text-decoration: line-through;
  }

  .del {
    background: #dd0000;
    color: #fff;
    border: none;
    padding: 5px 9px;
    /*border-radius: 30% 20% 30% 0%;*/
    border-radius: 50%;
    cursor: pointer;
    float: right;
  }
</style>