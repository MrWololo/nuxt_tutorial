<template>
  <div class="container">
    <h4 class="header">{{ title }}</h4>
    <p class="snippet">
      {{ snippet }}
    </p>
    <div class="cards-container">
      <CardsLargeCard
        v-for="card in cards"
        :key="card.id"
        :id="card.id"
        :title="card.title"
        :snippet="card.snippet"
        :image="card.image"
      />
    </div>
  </div>
</template>

<script>
import { defineComponent } from "~/node_modules/@nuxtjs/composition-api/lib/entrypoint";

export default defineComponent({
  props: { title: String, snippet: String, cards: Array[Object] }
  // setup(props) {
  //   const section = props.cardsSection;
  //   return { section };
  // }
});
</script>

<style scoped>
.container {
  margin-top: 2rem;
}
.header {
  font-weight: 700;
  font-size: 1.5rem;
}
.snippet {
  color: grey;
  margin-bottom: 1.5rem;
}
.cards-container {
  display: flex;
  justify-content: space-between;
}
</style>
