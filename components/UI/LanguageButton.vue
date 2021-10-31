<template>
  <div class="ml-1 mt-4">
    <NuxtLink to="/">
      <FlagSVG />
    </NuxtLink>
  </div>
</template>

<script>
import FlagSVG from "~/components/svgs/FlagSVG.vue";

export default {
  components: {
    FlagSVG,
  },
};
</script>

<style></style>
