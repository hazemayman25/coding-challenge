<template>
  <div class="w-[80%] h-[7px]">
    <div class="bar-value" :style="{ width: `${percentage * 100}%` }"></div>
  </div>
</template>

<script>
export default {
  props: ["percentage"],
};
</script>

<style scoped>
div {
  background-color: #e0e2e2;
  border-radius: 20px;
}

.bar-value {
  width: 100%;
  height: 100%;
  background-color: #79b753;
  border-radius: 20px;
}
</style>
