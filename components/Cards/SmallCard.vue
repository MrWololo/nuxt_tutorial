<template>
  <Nuxt-link :to="`/products/${id}`" class="card-container">
    <!-- <img :src="require(`@/assets/images/${image}`)" alt="" class="image" /> -->
    <div
      class="image"
      :style="{
        backgroundImage: 'url(' + require(`@/assets/images/${image}`) + ')',
      }"
    ></div>
  </Nuxt-link>
</template>

<script>
export default {
  props: {
    id: Number,
    image: String,
  },
};
</script>

<style scoped>
.card-container {
  width: 24%;
  height: 12.5rem;
  border-radius: 0.5rem;
  overflow: hidden;
  margin-bottom: 1.5rem;
  cursor: pointer;
  object-fit: cover;
  transition: 0.2s;
}
.card-container:hover {
  width: 25%;
  height: 13rem;
  margin-bottom: 1rem;
}
.image {
  width: 100%;
  height: 100%;
  background-size: cover;
  background-position: center;
}
</style>
