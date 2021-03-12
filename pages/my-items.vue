<template>
  <div>
    <MyItem v-for="item in myRentals" :key="item.id" :item="item" />
  </div>
</template>

<script>
import {
  defineComponent,
  useStore
} from "~/node_modules/@nuxtjs/composition-api/lib/entrypoint";

export default defineComponent({
  layout: "no-nav",
  setup() {
    const { myRentals } = useStore().state;
    return { myRentals };
  }
});
</script>

<style scoped>
</style>