<template>
  <div class="flex">
    <TheNavBar :isSelected="false" />
  </div>
</template>

<script>
import TheNavBar from "~/components/TheNavBar.vue";

export default {
  components: {
    TheNavBar,
  },
  data() {
    return {
      isSelected: false,
    };
  },
};
</script>
