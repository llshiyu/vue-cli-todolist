<template>
  <div class="todo-list">
    <li @click="handleDelete" title="点击删除">{{content}}</li>
  </div>
</template>

<script>
export default {
  name: 'TodoList',
  props: ['content', 'index'],
  methods: {
    handleDelete () {
      this.$emit('delete', this.index)
    }
  }
}
</script>

<style scoped>
.todo-list{
  margin-top: 10px;
}
  .todo-list li{
    cursor: pointer
  }
</style>
