<template>
  <input
    :value="modelValue"
    @input="$emit('update:model-value', +$event.target.value)"
    class="input"
    type="text"
  />
</template>

<script>
export default {
  props: {
    modelValue: {
      type: Number,
    },
  },
};
</script>

<style lang="scss" scoped>
.input {
  padding: 0.5rem 1rem;
  border: none;
  background-color: #fff;
  border-radius: 1rem;
  filter: drop-shadow(2px 2px 4px #aaa);

  &:focus-visible {
    outline: none;
  }
}
</style>
