<template>
  <div class="review-card">
    <div class="image-container">
      <img :src="picture" alt="" />
    </div>
    <div class="text-container">
      <h6>{{ username }}</h6>
      <p>
        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Assumenda iure nesciunt
        rerum ducimus blanditiis, aliquam deserunt dolore laborum eum sunt esse nihil
        commodi, harum eligendi. Velit esse explicabo accusantium voluptatem.
      </p>
    </div>
  </div>
</template>

<script>
export default {
  props: { picture: String, username: String },
};
</script>

<style scoped>
.review-card {
  margin-top: 1.5rem;
  height: 4rem;
  display: flex;
}
.text-container {
  margin-left: 2rem;
}
img {
  width: 4rem;
  height: 4rem;
  border-radius: 100%;
}
p {
  color: grey;
}
</style>
