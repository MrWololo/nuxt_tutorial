<template>
  <div>
    <!-- <b-button id="show-btn" @click="showModal"> Open Modal </b-button> -->
    <b-button id="toggle-btn" @click="toggleModal"> Rent </b-button>

    <b-modal ref="myModal" hide-footer title="Using Component Methods">
      <div class="calendar-container">
        <p class="text-container">
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. Animi,
          molestiae assumenda voluptate odio rem quod exercitationem consequatur
          adipisci libero minima illo quidem ex cupiditate dolore. Tempora
          perferendis saepe commodi at!
        </p>

        <vc-date-picker :value="null" color="indigo" is-dark is-range />
      </div>

      <b-button
        id="show-btn"
        variant="outline-danger"
        @click="
          () => {
            addItem(id);
            hideModal();
          }
        "
      >
        Order
      </b-button>
    </b-modal>
  </div>
</template>

<script>
import {
  defineComponent,
  ref,
  useStore
} from "~/node_modules/@nuxtjs/composition-api/lib/entrypoint";

export default defineComponent({
  props: {
    id: Number
  },
  setup() {
    const myModal = ref();
    const store = useStore();

    // const showModal = () => {
    //   myModal.value.show();
    // };
    const hideModal = () => {
      myModal.value.hide();
    };
    const toggleModal = () => {
      myModal.value.toggle("#toggle-btn");
    };

    const addItem = id =>
      store.commit({
        type: "addItem",
        id: id
      });

    return {
      myModal,
      hideModal,
      toggleModal,
      addItem
    };
  }
});
</script>

<style scoped>
button {
  width: 100%;
  border: none;
  padding: 1rem 8rem;
  color: white;
  font-weight: 700;
  border-radius: 100rem;
  background-color: rgb(231, 97, 44);
  transition: 0.5s;
}
.calendar-container {
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
}
p {
  color: grey;
}
.text-container {
  padding: 0.5rem;
}
</style>
