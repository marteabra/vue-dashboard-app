<template>
  <div class="list-item">
    <button
      @click="emitDone"
      class="list-item__done"
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
    //text: { type: String, default: "New Task" },
    done: { type: Boolean, default: false },
    task: { type: Object },
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
.list-item button {
  border: none;
  width: 28px;
  height: 20px;
  margin: 10px;
  font-weight: bold;
}

.list-item__task {
  display: flex;
  margin: 10px;
  width: 100%;
  height: 20px;
}

.list-item__done {
  background: grey;
  border-radius: 50%;
}

.list-item__done--checked {
  background: green;
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

.list-item input {
  border-radius: 5px;
  border: 1px solid rgba(0, 0, 0, 0.6);
  width: 90%;
}

.list-item__done--checked {
  background: rgb(19, 143, 19);
}
</style>