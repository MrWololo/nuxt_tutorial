<template>
  <nav class="navbar navbar-expand-lg navbar-dark bg-dark padding">
    <Nuxt-link class="navbar-brand" to="/"> Firengii </Nuxt-link>
    <button
      class="navbar-toggler"
      type="button"
      data-toggle="collapse"
      data-target="#navbarSupportedContent"
      aria-controls="navbarSupportedContent"
    >
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse ml-auto" id="navbarSupportedContent">
      <ul class="navbar-nav ml-auto">
        <li class="nav-item active">
          <Nuxt-link to="/products" class="nav-link">
            Products
            <span class="sr-only">(current)</span>
          </Nuxt-link>
        </li>
        <li class="nav-item active">
          <Nuxt-link to="/my-items" class="nav-link">
            My Items
            <span class="sr-only">(current)</span>
          </Nuxt-link>
        </li>
      </ul>
    </div>
  </nav>
</template>

<script>
export default {
  setup() {
    return {};
  }
};
</script>

<style scoped>
.padding {
  padding: 1.5rem;
  background-color: black;
}
.nav-left {
  margin-left: auto;
}
</style>
