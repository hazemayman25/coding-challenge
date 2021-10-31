<template>
  <div class="flex">
    <TheNavBar :isSelected="true" />
    <div class="flex flex-col header-grow">
      <InvOppHeader :numOfOpps="res.length" />
      <Tabs />
      <div class="flex flex-row flex-wrap container">
        <OppCard v-for="(obj, index) of res" :key="index" :opp="obj" />
      </div>
    </div>
  </div>
</template>

<script>
import TheNavBar from "~/components/TheNavBar.vue";
import InvOppHeader from "~/components/InvOppHeader.vue";
import OppCard from "~/components/UI/OppCard.vue";
import Tabs from "~/components/UI/Tabs.vue";

export default {
  components: {
    TheNavBar,
    InvOppHeader,
    OppCard,
    Tabs,
  },
  asyncData(context, callback) {
    fetch("https://prime-crowd.com/api/mock/rounds")
      .then((res) => res.json())
      .then((res) => {
        callback(null, { res });
      })
      .catch((err) => {
        console.log(err);
      });
  },
};
</script>

<style scoped>
.header-grow {
  flex-grow: 1;
}
</style>
