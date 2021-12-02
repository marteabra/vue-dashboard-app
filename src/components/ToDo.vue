<template>
  <div class="todo-container">
    <div class="todo">
      <div class="todo__title">{{ title }}</div>

      <hr class="todo__break" />
      <div class="todo__task" v-for="task in tasks">
        <button class="todo__task--done" aria-label="Done"></button>
        <div>{{ task.text }}</div>
        <button class="todo__task--remove-task" aria-label="Remove">X</button>
      </div>
      <button @click="addTask" class="todo__add-task">+</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: "MY LIST",
      tasks: [{ text: "This is a task", done: false }],
      ui: {
        clickMessage: "click to add a new task",
      },
    };
  },

  computed: {
    doneTasks() {
      return this.tasks.filter((task) => task.done === true);
    },
  },

  methods: {
    addTask() {
      this.task.push({ text: "new task", done: false });
    },

    removeTask() {},

    markTaskAsDone() {},
  },
};
</script>

<style>
.todo-container {
  background: indianred;
  position: relative;
  width: 30vw;
  padding: 1em;
}

.todo {
  position: absolute;
  height: 50vh;
  width: 28vw;
  background: lightgray;
}

.todo__title {
  text-align: center;
  margin: 10px;
  font-size: 20px;
}

.todo__add-task {
  position: absolute;
  bottom: 0;
  right: 0;
  padding: 0.5em;
}

.todo__task {
  display: flex;
  justify-content: space-between;
  padding: 0.5em;
  background: white;
}

.todo__task--remove-task {
  border-radius: 5px;
  background: grey;
  height: 25px;
  width: 25px;
  border: 0;
  font-size: 1em;
}

.todo__task--done {
  border-radius: 100%;
  border: 1px solid black;
  height: 25px;
  width: 25px;
}

.todo__add-task {
  background-color: transparent;
  font-size: 1.3em;
  border: 0;
}
</style>