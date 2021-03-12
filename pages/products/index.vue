<template>
  <div>
    <div class="container">
      <DisplaysLargeCardDisplay
        v-for="largeCardInfo in largeCardSections.slice(0, 1)"
        :key="`large${largeCardInfo.id}`"
        :title="largeCardInfo.title"
        :snippet="largeCardInfo.snippet"
        :cards="largeCardInfo.cards"
      />
      <DisplaysSmallCardDisplay
        v-for="smallCardInfo in smallCardSections"
        :key="`small${smallCardInfo.id}`"
        :title="smallCardInfo.title"
        :cards="smallCardInfo.cards"
      />
    </div>
  </div>
</template>

<script>
import { largeCardSections, smallCardSections } from "@/assets/data.js";
import { defineComponent } from "~/node_modules/@nuxtjs/composition-api/lib/entrypoint";
export default defineComponent({
  setup() {
    return { largeCardSections, smallCardSections };
  }
});
</script>

<style scoped>
</style>