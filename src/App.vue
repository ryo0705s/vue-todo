<template>
  <div>
    <h1>todoアプリ</h1>
    <input v-model="todo" />
    <button @click="add">追加</button>
    <ul>
      <li v-for="(todo, index) in todos" :key="index">
        {{ todo }}<button @click="remove">X</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      todo: "",
      todos: [],
    };
  },

  methods: {
    add() {
      this.todos.push(this.todo);
      this.todo = "";
    },
    remove(index) {
      this.todos.splice(index, 1);
    },
  },
};
</script>
