<template>
  <header>
    <h1>{{ title }}</h1>
    <Button text="Add Task" color="#ffa309" />
  </header>
</template>



<script>
import Button from "./Button.vue";
export default {
  name: "Header",
  props: {
    title: String,
  },
  components: {
    Button,
  },
};
</script>

<style scoped>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 10px;
}
h1 {
  font-style: normal;
  font-weight: 600;
  font-size: 18px;
}
</style> 




