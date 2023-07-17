<template>
  <button :style="{ backgroundColor: bgColor }" class="btn">
    <slot></slot>
  </button>
</template>

<script>
export default {
  props: {
    bgColor: String,
  },
};
</script>

<style lang="scss" scoped>
.btn {
  padding: 0.5rem 1rem;
  background-color: rgb(9, 136, 247);
  border-radius: 1rem;
  color: #fff;
  border: none;
  cursor: pointer;
}
</style>
