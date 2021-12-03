<template>
  <div class="todo-container">
    <div class="todo">
      <div class="todo__title">{{ title }}</div>

      <hr class="todo__break" />

      <div class="todo__content">
        <div class="todo__items">
          <TodoItem
            @test-event="onTestEvent"
            v-for="task in pendingTasks"
            :task="task"
          />
        </div>

        <hr class="todo__separator" />

        <div class="todo-items__done">
          <Toodoitem v-for="task in doneTasks" :task="task" />
        </div>
      </div>
      <button @click="addTask" class="todo__add-task">+</button>
    </div>
  </div>
</template>

<script>
import TodoItem from "../components/TodoItem.vue";

export default {
  components: {
    TodoItem,
  },

  data() {
    return {
      title: "MY LIST",
      tasks: [{ text: "This is a task", done: false }],
      id: 0,
    };
  },

  computed: {
    pendingTasks() {
      return this.tasks.filter((task) => task.done === false);
    },

    doneTasks() {
      return this.tasks.filter((task) => task.done === true);
    },
  },

  methods: {
    onTestEvent(data) {
      console.log("hei");
    },

    addTask() {
      this.tasks.push({ id: this.id, text: this.id, done: false });
      this.id++;
    },

    removeTask(id) {
      const taskIndex = this.tasks.findIndex((task) => task.id === id);
      this.tasks.splice(taskIndex, 1);
    },

    markTaskAsDone() {
      const taskIndex = this.tasks.findIndex((task) => task.id === id);
      this.tasks[taskIndex].done = !this.tasks[taskIndex].done;
    },

    id() {
      return Math.random().toString(36).slice(2);
    },
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

.list-item {
  display: flex;
  width: 100%;
  justify-content: space-between;
}

.todo {
  position: absolute;
  height: 50vh;
  width: 90%;
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

.todo__items {
  display: grid;
  width: 100%;
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