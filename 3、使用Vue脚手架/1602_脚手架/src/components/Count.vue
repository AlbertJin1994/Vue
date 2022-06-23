<template>
  <div>
    <h1>当前求和为：{{ sum }}</h1>
    <select v-model.number="num">
      <!-- 
        通过v-bind语法，value的值都是js表达式，那么就会是数字类型
        <option :value="1">1</option> 
        -->
      <option value="1">1</option>
      <option value="2">2</option>
      <option value="3">3</option>
      <option value="4">4</option>
      <option value="5">5</option>
    </select>
    <button @click="increment">+</button>
    <button @click="decrement">-</button>
    <button @click="incrementOdd">奇数再加</button>
    <button @click="incrementWait">等一会儿再加</button>
  </div>
</template>

<script>
export default {
  name: "Count",
  data() {
    return {
      num: 1,
      sum: 0,
    };
  },
  methods: {
    increment() {
      this.sum = this.sum + this.num;
    },
    decrement() {
      this.sum = this.sum - this.num;
    },
    incrementOdd() {
      if (this.sum % 2) {
        this.sum = this.sum + this.num;
      }
    },
    incrementWait() {
      setTimeout(() => {
        this.sum = this.sum + this.num;
      }, 700);
    },
  },
};
</script>

<style>
button {
  margin-left: 10px;
}
</style>
