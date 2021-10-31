<template>
  <div class="flex flex-row justify-between header-width header-height">
    <h1 class="ml-7 mt-4">Investment Opportunities ({{ numOfOpps }})</h1>
    <div class="flex flex-row justify-start items-center mr-15">
      <UserInfo />
      <NotificationButton />
      <LanguageButton />
    </div>
  </div>
</template>

<script>
import UserInfo from "~/components/UserInfo.vue";
import NotificationButton from "~/components/NotificationButton.vue";
import LanguageButton from "~/components/UI/LanguageButton.vue";

export default {
  props: ["numOfOpps"],
  components: {
    UserInfo,
    NotificationButton,
    LanguageButton,
  },
};
</script>

<style scoped>
.header-width {
  width: 100%;
}

.header-height {
  height: 7.5%;
}
</style>
