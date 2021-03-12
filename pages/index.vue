<template>
  <div>
    <div class="container">
      <Hero />
      <DisplaysLargeCardDisplay
        v-for="cardInfo in largeCardSections"
        :key="`large${cardInfo.id}`"
        :title="cardInfo.title"
        :snippet="cardInfo.snippet"
        :cards="cardInfo.cards"
      />
      <DisplaysSmallCardDisplay
        v-for="cardInfo in smallCardSections"
        :key="`small${cardInfo.id}`"
        :title="cardInfo.title"
        :cards="cardInfo.cards"
      />
    </div>
  </div>
</template>

<script>
import { defineComponent } from "@nuxtjs/composition-api";
import { largeCardSections, smallCardSections } from "@/assets/data.js";
export default defineComponent({
  setup() {
    return {
      largeCardSections,
      smallCardSections
    };
  }
});
</script>

<style></style>
