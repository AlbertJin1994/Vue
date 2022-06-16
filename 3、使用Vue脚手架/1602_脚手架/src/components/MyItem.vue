<template>
  <li>
    <label>
      <!-- <input type="checkbox" :checked="todo.done" @click="checkHandle(todo.id)" /> -->
      <input type="checkbox" :checked="todo.done" @change="checkHandle(todo.id)" />
      <!-- 
        改变对象中的属性数据并不会被Vue监视发现（即不会报错），
          但是仍然不建议这么使用，因为有点违法原则，因为修改了props
        -->
      <!-- <input type="checkbox" v-model="todo.done" /> -->
      &nbsp;
      <span>{{ todo.title }}</span>
    </label>
    <button class="btn btn-danger" style="display: none">删除</button>
  </li>
</template>

<script>
export default {
  name: "MyItem",
  props: ["todo", "checkTodo"],
  methods: {
    checkHandle(id) {
      this.checkTodo(id);
    },
  },
};
</script>

<style scoped>
/*item*/
li {
  list-style: none;
  height: 36px;
  line-height: 36px;
  padding: 0 5px;
  border-bottom: 1px solid #ddd;
}

li label {
  float: left;
  cursor: pointer;
}

li label li input {
  vertical-align: middle;
  margin-right: 6px;
  position: relative;
  top: -1px;
}

li button {
  float: right;
  display: none;
  margin-top: 3px;
}

li:before {
  content: initial;
}

li:last-child {
  border-bottom: none;
}
</style>
