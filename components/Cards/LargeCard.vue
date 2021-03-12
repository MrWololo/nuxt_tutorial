<template>
  <Nuxt-link :to="`/products/${id}`" class="card">
    <!-- <img
      :src="require(`@/assets/images/${image || 'fe1.jpg'}`)"
      alt="fe"
      class="image"
    /> -->
    <div
      class="image"
      :style="{
        backgroundImage: 'url(' + require(`@/assets/images/${image}`) + ')',
      }"
    ></div>
    <h3 class="header">{{ title }}</h3>
    <p class="snippet">{{ snippet }}</p>
  </Nuxt-link>
</template>

<script>
import { defineComponent } from "~/node_modules/@nuxtjs/composition-api/lib/entrypoint";

export default defineComponent({
  props: { id: Number, title: String, snippet: String, image: String }
});
</script>

<style scoped>
.card {
  width: 31.5%;
  height: 25rem;
  border: none;
  overflow: hidden;
  padding: 0;
  cursor: pointer;
  object-fit: cover;
  object-position: 0 0;
  transition: 0.2s;
}
.card:hover {
  text-decoration: none;
  width: 33%;
  height: 26.5rem;
  margin-bottom: -1.5rem;
}
.image {
  height: 65%;
  border-radius: 0.5rem;
  background-position: center;
  background-size: cover;
}
.header {
  color: black;
  font-size: 1.15rem;
  margin-top: 0.4rem;
  text-decoration: none;
}
.snippet {
  color: grey;
}
</style>