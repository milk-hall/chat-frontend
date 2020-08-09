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
  width: 80vw;
  flex: 1;
  min-height: 720px;
  margin: 50px auto;
  text-align: center;
  align-items: center;
  justify-content: center;
  display: flex;
}
</style>
