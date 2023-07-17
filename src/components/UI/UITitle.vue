<template>
  <h1 class="header-gradient">
    <slot></slot>
  </h1>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.header-gradient {
  display: flex;
  text-align: center;
  background-image: linear-gradient(to right, #17d576, #00aaff);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  color: transparent;
  font-size: 5rem;
  align-items: center;
  cursor: pointer;
  line-height: 73px;
}

@media screen and (max-width: 414px) {
  .header-gradient {
    font-size: 2rem;
  }
}
</style>
