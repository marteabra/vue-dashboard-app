<template>
  <div class="todo-container">
    <div class="todo">
      <div class="todo__title">{{ title }}</div>

      <div class="todo__content">
        <div class="todo__items">
          <TodoItem
            @done-task="doneTask"
            @remove-task="removeTask"
            v-for="task in tasks"
            :task="task"
          />
        </div>
      </div>
      <button @click="addTask" class="todo__add-task">+ Add new task</button>
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
      title: "TO DO LIST",
      tasks: [],
    };
  },

  computed: {
    doneTasks() {
      return this.tasks.filter((task) => task.done === true);
    },
  },

  methods: {
    addTask() {
      this.tasks.push({ id: this.id(), text: "", done: false });
    },

    removeTask(task) {
      const taskIndex = this.tasks.findIndex(
        (currentTask) => task.id === currentTask.id
      );
      this.tasks.splice(taskIndex, 1);
    },

    doneTask(task) {
      const taskIndex = this.tasks.findIndex(
        (currentTask) => currentTask.id === task.id
      );
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

.todo {
  position: absolute;
  height: 50vh;
  width: 90%;
  background: rgb(255, 255, 255);
}

.todo-content {
  position: relative;
  overflow: scroll;
}

.todo__title {
  text-align: center;
  margin: 10px;
  font-size: 20px;
}

.todo__add-task {
  position: absolute;
  bottom: 0;
  width: 100%;
  padding: 0.5em;
  font-size: 1em;
  border: 0;
}

.todo__items {
  display: grid;
  width: 100%;
  padding: 0.5em;
}
</style>