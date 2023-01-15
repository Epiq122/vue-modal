<template>
  <h1>{{ title }}</h1>
  <input ref="name" type="text" />
  <button @click="handleClick">Click Me</button>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      title: "My First Vue App!",
    };
  },
  methods: {
    handleClick() {
      // this gives a reference to the DOM element up to top in the input field
      console.log(this.$refs.name);
      // this adds a class to the input field
      this.$refs.name.classList.add("active");
      // this adds focus to the input field
      this.$refs.name.focus();
    },
  },
};
</script>

<style scoped></style>
