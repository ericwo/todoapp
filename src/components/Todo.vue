<template>
  <div>
    <input v-model="newTodo" v-on:keyup.enter="addTodo">
    <ul>
      <li v-for="todo in todos">
        <span>{{ todo.text }}</span>
        <button v-on:click="removeTodo($index)">X</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data () {
    return {
      todos: [
        { text: 'Add some todos' }
      ]
    }
  },
  methods: {
    addTodo: function () {
      var text = this.newTodo.trim()
      if (text) {
        this.todos.push({ text: text })
        this.newTodo = ''
      }
    },
    removeTodo: function (index) {
      this.todos.splice(index, 1)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1 {
  color: #42b983;
}
</style>
