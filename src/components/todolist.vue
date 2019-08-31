<template>
  <div>
    <ul class="list-group">
      <li
        class="list-group-item"
        v-for="item in todoList"
        :key="item.id"
      >{{item.id}} {{item.name}} {{item.time}}</li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    todoList: Array
  }
};
</script>
