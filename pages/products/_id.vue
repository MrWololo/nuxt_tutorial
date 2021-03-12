<template>
  <div>
    <div v-if="product" class="container py-5">
      <div class="hero-container">
        <div
          class="image"
          :style="{
            backgroundImage:
              'url(' + require(`@/assets/images/${product.image}`) + ')',
          }"
        ></div>
        <div class="info-box">
          <div>
            <h1>{{ product.title }}</h1>
            <p class="snippet">{{ product.snippet }}</p>
          </div>
          <RentModal :id="product.id" />
        </div>
      </div>

      <div class="whats-included-container">
        <div class="included-container">
          <h6>Super Effective</h6>
          <p>
            Lorem ipsum dolor sit amet, consectetur adipisicing elit. Non culpa
            est iusto vero voluptatem provident pariatur possimus, neque
            sapiente animi quae, odio nihil minus? Ipsam obcaecati est molestias
            blanditiis odio.
          </p>
        </div>
        <div class="included-container">
          <h6>Clean & Tidy</h6>
          <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis harum
            deserunt quisquam aliquam dicta! Hic eaque sint tempora a amet ipsam
            rerum iusto saepe sunt ea? Neque maxime enim modi.
          </p>
        </div>
        <div class="included-container">
          <h6>Cancel Anytime</h6>
          <p>
            Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dolore
            dolorum porro repudiandae veritatis laudantium temporibus. Eum hic
            accusantium, vel eligendi exercitationem quos itaque explicabo
            facilis temporibus neque fugit architecto ut!
          </p>
        </div>
        <div class="included-container">
          <h6>Satisfaction Guaranteed</h6>
          <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Cum magnam
            libero ipsa aliquam harum corrupti, atque alias laboriosam
            consectetur voluptate maiores voluptates nesciunt autem in odit non
            modi fugit eum.
          </p>
        </div>
      </div>

      <div class="description-container">
        <p>{{ product.description }}</p>
      </div>
      <Reviews />
    </div>

    <div v-else class="container-padding"><PageNotFound /></div>
  </div>
</template>

<script>
import {
  defineComponent,
  useRoute,
  useStore
} from "~/node_modules/@nuxtjs/composition-api/lib/entrypoint";

export default defineComponent({
  setup() {
    const routeID = useRoute().value.params.id;
    const product = useStore().getters.getProductById(routeID);

    return { product };
  }
});
</script>

<style scoped>
.hero-container {
  display: flex;
  justify-content: space-between;
}
.image {
  width: 59%;
  height: 25rem;
  background-position: center;
  background-size: cover;
}
.info-box {
  display: flex;
  flex-direction: column;
  width: 39%;
  background-color: rgba(207, 201, 201, 0.322);
  padding: 1rem;
  border-radius: 0.5rem;
  align-items: center;
  justify-content: space-between;
}
.whats-included-container {
  border-bottom: 0.1rem solid rgba(128, 128, 128, 0.151);
}
.description-container {
  border-bottom: 0.1rem solid rgba(128, 128, 128, 0.151);
  padding-bottom: 2rem;
  margin-top: 2rem;
}
.included-container {
  margin-top: 1.5rem;
}
</style>