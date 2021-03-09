<template>
  <div class="container">
    <Hero />
    <!-- <LargeCardDisplay
      v-for="number in largeCardInfo"
      :key="number"
      :cardsSections="cardInfo"
    /> -->
    <p v-for="cardInfo in largeCardInfo" :key="cardInfo.id">{{ cardInfo }}</p>
  </div>
</template>

<script>
import { defineComponent } from "@nuxtjs/composition-api";
import { largeCardSections } from "@/assets/data.js";
export default defineComponent({
  setup() {
    let largeCardInfo = largeCardSections;

    return {
      largeCardInfo
    };
  }
});
</script>

<style>
</style>
