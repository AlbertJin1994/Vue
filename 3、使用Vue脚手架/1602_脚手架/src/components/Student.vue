<template>
  <div>
    <h2>{{ msg }}</h2>
    <h2>学生姓名：{{ name }}</h2>
    <h2>学生年龄：{{ myAge + 1 }}</h2>
    <h2>学生性别：{{ sex }}</h2>
    <button @click="addAge">点击年龄+1</button>
  </div>
</template>

<script>
export default {
  name: "Student",
  data() {
    return {
      msg: "Hello World !",
      myAge: this.age,
    };
  },
  methods: {
    addAge() {
      this.myAge++;
    },
  },
  //简单声明接收
  //   props: ["name", "age", "sex"],

  //接收的同时对数据进行类型限制
  //   props: {
  //     name: String,
  //     age: Number,
  //     sex: String,
  //   },

  //接收的同时对数据：进行类型限制+默认值的指定+必要性的限制
  props: {
    name: {
      type: String,
      require: true,
    },
    age: {
      type: Number,
      default: 99,
    },
    sex: {
      type: String,
      require: true,
    },
  },
};
</script>

<style></style>
