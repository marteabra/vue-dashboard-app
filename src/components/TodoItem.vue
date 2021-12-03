<template>
  <div class="list-item">
    <button class="list-item__done" aria-label="Done">O</button>
    <div class="list-item__task">{{ task.text }}</div>
    <button class="list-item__remove" @click="removeTask" aria-label="Remove">
      X
    </button>
  </div>
</template>

<script>
export default {
  props: {
    text: { type: String, default: "New Task" },
    done: { type: Boolean, default: false },
    task: { type: Object },
  },

  methods: {
    removeTask() {},
  },
};
</script>