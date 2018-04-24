<template>
  <div class="hello">
    <h1>{{msg}}</h1>
    <input type="text" v-model="inputValue"/>
    <button @click="handleSubmit">提交</button>
    <ul>
      <TodoList
        v-for="(item, index) of list"
        :key="index"
        :content="item"
        :index="index"
        @delete="handleDelete"
      ></TodoList>
    </ul>

  </div>
</template>

<script>
import TodoList from './TodoList'

export default {
  name: 'HelloWorld',
  components: {
    TodoList
  },
  data () {
    return {
      msg: 'This is vue-cli todoList',
      inputValue: '',
      list: []
    }
  },
  methods: {
    handleSubmit () {
      this.list.push(this.inputValue)
      this.inputValue = ''
    },
    handleDelete (index) {
      this.list.splice(index, 1)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<!-- 加‘scoped' 样式只对自身有效 不会影响其他组件 -->
<style scoped>
  h1, h2 {
    font-weight: normal;
  }

  ul {
    list-style-type: none;
    padding: 0;
  }

  li {
    display: inline-block;
    margin: 0 10px;
  }

  a {
    color: #42b983;
  }
</style>
