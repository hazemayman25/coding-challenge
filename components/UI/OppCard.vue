<template>
  <section class="w-[330px] h-[fit-content] rounded-lg bg-white mb-11 ml-5">
    <img :src="opp.banner" alt="" class="h-[110px] w-[330px] mb-4" />
    <span class="py-2 px-3 rounded-lg ml-3">{{
      daysRemOrPassed(opp["round_end"])
    }}</span>
    <h1 class="font-medium text-2xl mt-2 ml-3">{{ opp.title }}</h1>
    <div class="ml-3">
      <div class="flex justify-start items-center">
        <h1 class="ml-1 text-xl font-medium light-green">
          {{ percentage(opp) }}%
        </h1>
        <p class="ml-6">{{ fundsRemaining(opp) }}&euro; left to fund</p>
      </div>
      <ProgressBar :percentage="percentage(opp) / 100" />
    </div>
    <p class="mt-3 ml-3 mb-3">
      {{ opp.teaser }}
    </p>
    <div class="flex justify-start">
      <OppStatus :status="opp.status" />
      <OppType :type="opp.type" />
    </div>
    <CardLineSVG />
    <div>
      <div class="flex justify-evenly mt-2">
        <NumberOfInvestors :investors="opp['investor_count']" />
        <FundingRound :goal="opp['investment_goal']" />
      </div>
      <div class="flex justify-center">
        <button
          class="w-[90%] py-3 rounded-md bg-[#063847] text-white mt-3 mb-3"
        >
          Learn more
        </button>
      </div>
    </div>
  </section>
</template>

<script>
import ProgressBar from "~/components/UI/ProgressBar.vue";
import OppStatus from "~/components/UI/OppStatus.vue";
import OppType from "~/components/UI/OppType.vue";
import CardLineSVG from "~/components/svgs/CardLineSVG.vue";
import NumberOfInvestors from "~/components/UI/NumberOfInvestors.vue";
import FundingRound from "~/components/UI/FundingRound.vue";

export default {
  props: ["opp"],
  components: {
    ProgressBar,
    OppStatus,
    OppType,
    CardLineSVG,
    NumberOfInvestors,
    FundingRound,
  },
  created() {
    console.log(this.opp);
  },
  computed: {
    percentage() {
      return (opp) => {
        return Math.floor(
          (parseInt(opp["current_investment"]) /
            parseInt(opp["investment_goal"])) *
            100
        );
      };
    },
    fundsRemaining() {
      return (opp) => {
        return (
          parseInt(opp["investment_goal"]) - parseInt(opp["current_investment"])
        );
      };
    },
    daysRemOrPassed() {
      return (time) => {
        var date1 = new Date(time);
        var date2 = new Date();

        // To calculate the time difference of two dates
        var Difference_In_Time = date1.getTime() - date2.getTime();

        // To calculate the no. of days between two dates
        var Difference_In_Days = Difference_In_Time / (1000 * 3600 * 24);

        return `${Math.ceil(Difference_In_Days)} days left`;
      };
    },
  },
};
</script>

<style scoped>
span {
  background-color: #00516c;
  color: white;
  margin-top: 1.5rem;
}

.light-green {
  color: #74b54e;
}
</style>
