<template>
  <div>
    <UI-title class="title">Finances for friends</UI-title>
    <my-form />
  </div>
</template>

<script>
import UITitle from "@/components/UI/UITitle.vue";
import MyForm from "./components/MyForm.vue";

export default {
  name: "App",
  components: {
    UITitle,
    MyForm,
  },
};
</script>

<style>
#app {
  display: flex;
  flex-direction: column;
  align-items: center;
  font-family: "Poppins", sans-serif;
  min-height: 100vh;
}

.title {
  margin-top: 3rem;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>
