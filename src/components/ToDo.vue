<template>
  <div class="todo-container">
    <div class="todo__title">{{ title }}</div>
    <div class="todo">
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
  position: relative;
  width: 30vw;
  height: 60vh;
  padding: 1em;
}

.todo-content {
  height: 300px;
}

.todo {
  position: absolute;
  height: 50vh;
  width: 90%;
  overflow-y: scroll;
}

.todo__title {
  position: ;
  margin-top: 0;
  margin-bottom: 10;
  width: 100%;
  text-align: center;
  font-size: 20px;
}

.todo__add-task {
  position: absolute;
  width: 100%;
  margin-top: 20px;
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