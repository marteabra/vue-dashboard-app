<template class="todo">
  <div class="list-item">
    <button
      @click="emitDone"
      :class="doneButtonClass"
      aria-label="Done"
    ></button>

    <div class="list-item__task">
      <input type="text" v-model="task.text" placeholder="New task" />
    </div>

    <button class="list-item__remove" @click="emitRemove" aria-label="Remove">
      X
    </button>
  </div>
</template>

<script>
export default {
  props: {
    task: { type: Object },
  },

  computed: {
    doneButtonClass() {
      return this.task.done
        ? "list-item__done--green"
        : "list-item__done--white";
    },
  },

  methods: {
    emitDone() {
      this.$emit("done-task", this.task);
    },

    emitRemove() {
      this.$emit("remove-task", this.task);
    },
  },
};
</script>

<style>
.list-item {
  display: flex;
  overflow: scroll;
  width: 100%;
  justify-content: space-between;
  background: rgb(189, 189, 189);
}

.list-item input {
  border-radius: 5px;
  border: 1px solid rgba(0, 0, 0, 0.6);
  width: 90%;
}

.list-item button {
  width: 28px;
  height: 20px;
  margin: 10px;
  font-weight: bold;
}

.list-item__done--green {
  background: rgba(82, 201, 82, 0.8);
}

.list-item__done--white {
  background: rgb(255, 255, 255);
}

.list-item button:nth-child(1) {
  border: 1px solid rgba(0, 0, 0, 0.5);
  border-radius: 50%;
}

.list-item button:nth-child(3) {
  border: none;
}

.list-item__task {
  display: flex;
  margin: 10px;
  width: 100%;
  height: 20px;
}

.list-item__task :nth-child(1) {
  flex-grow: 1;
}
.list-item__task :nth-child(2) {
  flex-grow: 3;
}
.list-item__task :nth-child(3) {
  flex-grow: 1;
}
</style>