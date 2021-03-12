<template>
  <div>
    <h3>Customer Reviews</h3>
    <div v-if="!fetchState.pending">
      <CardsReviewCard
        v-for="reviewer in reviewers.results"
        :key="reviewer.login.uuid"
        :picture="reviewer.picture.large"
        :username="reviewer.login.username"
      />
    </div>
    <div v-else>Loading...</div>
  </div>
</template>

<script>
import {
  defineComponent,
  useFetch,
  ref,
} from "~/node_modules/@nuxtjs/composition-api/lib/entrypoint";
export default defineComponent({
  setup() {
    const reviewers = ref({ results: Array });

    const { fetchState } = useFetch(async () => {
      reviewers.value = await fetch("https://randomuser.me/api/?results=5").then((res) =>
        res.json()
      );
    });

    // fetchUtils.fetch();

    return { reviewers, fetchState };
  },
});
</script>

<style scoped></style>
