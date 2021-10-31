<template>
  <div class="flex flex-col header-grow">
    <InvOppHeader :numOfOpps="res.length" />
    <Tabs />
    <div class="flex flex-row flex-wrap container">
      <OppCard v-for="(obj, index) of opps" :key="index" :opp="obj" />
    </div>
  </div>
</template>

<script>
import InvOppHeader from "~/components/InvOppHeader.vue";
import Tabs from "~/components/UI/Tabs.vue";
import OppCard from "~/components/UI/OppCard.vue";

export default {
  components: {
    InvOppHeader,
    Tabs,
    OppCard,
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
  computed: {
    opps() {
      switch (this.$route.params.status) {
        case "active":
          return [this.res[0], this.res[1]];
        case "coming_soon":
          return [this.res[2]];
      }
    },
  },
  mounted() {
    setTimeout(() => {
      console.log(this.opps);
    }, 2000);
  },
};
</script>

<style scoped>
.header-grow {
  flex-grow: 1;
}
</style>
