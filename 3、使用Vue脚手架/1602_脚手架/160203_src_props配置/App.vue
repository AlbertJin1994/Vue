<template>
  <div>
    <Student name="Ryu" sex="男" :age="18" />
    <Student name="Alvin" sex="女" />
  </div>
</template>

<script>
import Student from "./components/Student.vue";
export default {
  name: "App",
  components: {
    Student,
  },
};
</script>

<style></style>
