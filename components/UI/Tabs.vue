<template>
  <div class="container ml-5 mt-13 mb-5">
    <ul class="flex justify-start mb-3">
      <li @click="changeLink">
        <NuxtLink
          class="ml-2 mr-2 font-medium opacity-40"
          :class="
            selectedLink === undefined ? 'selected' : 'unselected hoverable'
          "
          to="/investment-opportunities"
          >All</NuxtLink
        >
      </li>
      <li @click="changeLink">
        <NuxtLink
          class="ml-2 mr-2 font-medium opacity-40"
          :class="
            selectedLink === 'active' ? 'selected' : 'unselected hoverable'
          "
          to="/investment-opportunities/active"
          >Active</NuxtLink
        >
      </li>
      <li @click="changeLink">
        <NuxtLink
          class="ml-2 mr-2 font-medium opacity-40"
          :class="
            selectedLink === 'coming_soon' ? 'selected' : 'unselected hoverable'
          "
          to="/investment-opportunities/coming_soon"
          >Coming Soon</NuxtLink
        >
      </li>
    </ul>
    <div>
      <div class="w-[100%] h-[4px] bg-[#e2e5e6]"></div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      selectedLink: this.$route.params.status,
    };
  },
  watch: {},
  methods: {
    changeLink() {
      this.selectedLink = this.$route.params.status;
      console.log(this.$route.params.status);
    },
  },
};
</script>

<style scoped>
.nuxt-link-active,
.hoverable {
  color: #063847;
  opacity: 1;
}

.unselected {
  color: #86959a;
}

.selected {
  color: #063847;
  opacity: 1;
  font-weight: bold;
}
</style>
