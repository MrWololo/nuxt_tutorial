<template>
  <div class="item-container">
    <div
      class="img"
      :style="{
        backgroundImage:
          'url(' + require(`@/assets/images/${item.image}`) + ')',
      }"
    ></div>

    <div class="text-container">
      <h4>{{ item.title }}</h4>
      <p>{{ item.description }}</p>
    </div>
  </div>
</template>

<script>
import { defineComponent } from "~/node_modules/@nuxtjs/composition-api/lib/entrypoint";

export default defineComponent({
  props: { item: Object }
});
</script>

<style scoped>
.item-container {
  display: flex;
  align-items: center;
  margin: 3rem 0;
}
.text-container {
  padding: 0 1rem;
}
.img {
  width: 120rem;
  height: 11rem;
  border-radius: 0.5rem;
  background-position: center;
  background-size: cover;
}
p {
  font-size: 0.85rem;
  color: grey;
}
</style>
