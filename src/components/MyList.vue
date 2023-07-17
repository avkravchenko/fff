<template>
  <ul>
    <li class="user-debt" v-for="user in users" :key="user.id">
      {{ `${user.name}: ${user.debt.toFixed(2)}` }}
    </li>
  </ul>
</template>

<script>
export default {
  props: {
    users: {
      type: Array,
      requiered: true,
    },
  },
};
</script>

<style lang="scss" scoped>
.user-debt {
  list-style: none;
}
</style>
