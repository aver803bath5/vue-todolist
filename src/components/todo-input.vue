<template>
  <form @submit.prevent="addTodo">
    <div class="form-group">
      <div class="input-group">
        <input
          class="form-control"
          id="todoInput"
          type="text"
          v-model="todoName"
          placeholder="Enter todo name"
        >
        <div class="input-group-append">
          <button type="submit" class="btn btn-primary">Submit</button>
        </div>
      </div>
    </div>
  </form>
</template>

<script>
export default {
  data() {
    return {
      id: 0,
      todoName: null
    };
  },
  methods: {
    addTodo() {
      if (this.todoName !== null) {
        const todoItem = {
          id: this.id,
          name: this.todoName,
          time: new Date()
        };
        this.$emit("addTodo", todoItem);
        this.todoName = null;
        this.id += 1;
      }
      this.todoName = null;
    }
  }
};
</script>

