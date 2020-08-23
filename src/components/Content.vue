<template>
  <div class="content">
    <slot></slot>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.content {
  background: url("/bg.png") no-repeat center;
  background-size: 100%;
  min-width: 80vw;
  flex: 1;
  height: 80vh;
  margin: 50px auto;
  text-align: center;
  align-items: center;
  justify-content: center;
  display: flex;
}
</style>
