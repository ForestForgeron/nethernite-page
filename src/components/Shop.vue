<template>
  <section class="shop">
    <div class="shop__navbar-wrapper">
      <Shop-Navbar />
    </div>

    <Shop-Bank />
  </section>
</template>

<script>
import ShopNavbar from "./ShopNavbar.vue";
import ShopBank from "./ShopBank.vue";
export default {
  name: "Shop",
  components: {
    ShopNavbar,
    ShopBank,
  },
};
</script>

<style lang="scss" scoped>
.shop {
  padding-top: 50px;

  display: flex;
  flex-direction: column;
  align-items: center;
}

@media screen and(min-width: 961px) {
  .shop {
    padding-top: 90px;
  }
}

@media screen and(max-width: 961px) {
  .shop {
    &__navbar-wrapper {
      margin-bottom: 10px;
    }
  }
}
</style>