<template>
  <div
    class="
      px-3
      py-1
      bg-[#f4f7f8]
      rounded-[50px]
      w-[fit-content]
      mr-2
      ml-4
      font-medium
    "
  >
    {{ status }}
  </div>
</template>

<script>
export default {
  props: ["status"],
};
</script>

<style></style>
