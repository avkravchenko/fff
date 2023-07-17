<template>
  <div class="check-item">
    <input
      :id="name"
      :name="name"
      :checked="modelValue"
      @change="$emit('update:model-value', $event.target.checked)"
      type="checkbox"
    />
    <label :for="name">{{ name }}</label>
  </div>
</template>

<script>
export default {
  props: {
    modelValue: [Boolean],
    name: {
      type: String,
      required: true,
    },
    checked: {
      type: Boolean,
    },
  },
};
</script>

<style lang="scss" scoped>
.check-item {
  display: flex;
  justify-content: flex-start;
  gap: 0.5rem;
}
</style>
