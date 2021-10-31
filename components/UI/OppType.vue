<template>
  <div
    class="
      px-3
      py-1
      bg-[#f4f7f8]
      rounded-[50px]
      w-[fit-content]
      ml-2
      font-medium
    "
  >
    {{ type }}
  </div>
</template>

<script>
export default {
  props: ["type"],
};
</script>

<style></style>
