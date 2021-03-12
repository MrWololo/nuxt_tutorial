<template>
  <div>
    <h1>Page not Found</h1>
    <img :src="require(`@/assets/images/${image}`)" alt="" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      image: "fe25.jpg"
    };
  }
};
</script>

<style scoped>
div {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 50rem;
  margin: 0 auto;
}
h1 {
  font-size: 7.5rem;
}
img {
  width: 15rem;
}
</style>