<template>
  <div class="demo">
    <h2 class="title">
      {{ title }}
    </h2>
    <div class="content">
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Demo',
  props: {
    title: {
      type: String,
      default: 'Demo',
    },
  },
}
</script>

<style scoped>
.demo {
  padding: 20px;
  border-radius: 5px;
  border: 1px solid #333;
  margin-bottom: 20px;
}
.title {
  font-size: 16px;
  font-weight: 500;
  text-align: center;
}
.content {
  margin-top: 20px;
  display: flex;
  align-items: center;
  flex-wrap: wrap;
  gap: 20px;
}
</style>
