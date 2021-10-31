<template>
  <div class="bg-white mt-0 h- bar-width">
    <img
      class="pl-7 mb-3 mt-3 cursor-pointer"
      src="~/assets/images/Logo.png"
      alt=""
    />
    <section>
      <ul>
        <li>
          <CockpitSVG />
          <NuxtLink class="ml-1 py-1" to="/">Cockpit</NuxtLink>
        </li>
        <li>
          <InvOppSVG />
          <NuxtLink class="ml-1 py-1" to="/investment-opportunities"
            >Investment Opportunities</NuxtLink
          >
        </li>
        <li>
          <MyInvSVG />
          <NuxtLink class="ml-1 py-1" to="/">My Investments</NuxtLink>
        </li>
      </ul>
    </section>
    <LineSVG />
    <section>
      <ul>
        <li>
          <KnowledgeCenterSVG />
          <NuxtLink class="ml-1 py-1" to="/">Knowledge Center</NuxtLink>
        </li>
        <li>
          <VenturePoolSVG />
          <NuxtLink class="ml-1 py-1" to="/">Venture Pool</NuxtLink>
        </li>
        <li>
          <FeeModelSVG />
          <NuxtLink class="ml-1 py-1" to="/">Fee Model</NuxtLink>
        </li>
      </ul>
    </section>
    <RecommendationBlock />
    <HelpBlock />
  </div>
</template>

<script>
import CockpitSVG from "~/components/svgs/CockpitSVG.vue";
import InvOppSVG from "~/components/svgs/InvOppSVG.vue";
import MyInvSVG from "~/components/svgs/MyInvSVG.vue";
import KnowledgeCenterSVG from "~/components/svgs/KnowledgeCenterSVG.vue";
import VenturePoolSVG from "~/components/svgs/VenturePoolSVG.vue";
import FeeModelSVG from "~/components/svgs/FeeModelSVG.vue";
import LineSVG from "~/components/svgs/LineSVG.vue";
import RecommendationBlock from "~/components/RecommendationBlock.vue";
import HelpBlock from "~/components/HelpBlock.vue";

export default {
  components: {
    CockpitSVG,
    InvOppSVG,
    MyInvSVG,
    KnowledgeCenterSVG,
    VenturePoolSVG,
    FeeModelSVG,
    LineSVG,
    RecommendationBlock,
    HelpBlock,
  },
};
</script>

<style scoped>
div {
  max-width: max-content;
}

.bar-width {
  min-width: fit-content;
}

li {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: flex-start;
  padding-top: 0.25rem;
  padding-bottom: 0.25rem;
  padding-left: 1.75rem;
}

li:hover {
  background-color: #063847;
  color: white;
}
</style>
