<template>
  <div
    class="
      ml-7
      mr-10
      container
      flex flex-col
      justify-center
      items-center
      mt-2
      mb-2
      rounded-lg
    "
  >
    <LikeSVG />
    <h3 class="mt-2 mr-4 ml-4">Recommend primeCROWD</h3>
    <button class="py-1 px-2 bg-white rounded-lg mb-5 mt-2">
      Invite Friends
    </button>
  </div>
</template>

<script>
import LikeSVG from "~/components/svgs/LikeSVG.vue";

export default {
  components: {
    LikeSVG,
  },
};
</script>

<style scoped>
div {
  background-image: linear-gradient(to right, #004055, #00516c);
}

h3 {
  color: white;
}
</style>
