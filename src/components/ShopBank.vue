<template>
  <section class="shop-bank">
    <h3 class="shop-bank__title">кристаллы незера</h3>
    <div class="shop-bank__list">
      <Card
        :cardImgSrc="card.imgSrc"
        :resourcesAmount="card.resourcesAmount"
        v-for="card in cards"
        :key="card.id"
      />
    </div>
  </section>
</template>

<script>
import Card from "./Card.vue";
export default {
  name: "ShopBank",
  components: {
    Card,
  },

  data() {
    return {
      cards: [
        {
          id: 0,
          imgSrc: "crystals_1.svg",
          resourcesAmount: "100",
        },
        {
          id: 1,
          imgSrc: "crystals_2.svg",
          resourcesAmount: "500",
        },
        {
          id: 2,
          imgSrc: "crystals_3.svg",
          resourcesAmount: "1000",
        },
        {
          id: 3,
          imgSrc: "crystals_1.svg",
          resourcesAmount: "1500",
        },
        {
          id: 4,
          imgSrc: "crystals_2.svg",
          resourcesAmount: "100",
        },
        {
          id: 5,
          imgSrc: "crystals_3.svg",
          resourcesAmount: "500",
        },
        {
          id: 6,
          imgSrc: "crystals_1.svg",
          resourcesAmount: "1000",
        },
        {
          id: 7,
          imgSrc: "crystals_2.svg",
          resourcesAmount: "1500",
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
.shop-bank {
  width: 72vw;
  min-width: 290px;
  height: 480px;
  padding-bottom: 30px;
  padding-top: 25px;

  background: #242333;
  box-shadow: 0px 20px 30px rgba(0, 0, 0, 0.5);
  border-radius: 0px 0px 10px 10px;

  overflow: scroll;
  scrollbar-width: none;

  &::-webkit-scrollbar {
    display: none;
  }

  &__title {
    font-size: 30px;
    font-weight: 700;
    text-transform: capitalize;
    text-align: center;

    color: #fff;
  }

  &__list {
    position: relative;
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
    justify-items: center;
    row-gap: 20px;

    max-height: 715px;
    margin-top: 25px;
  }
}

@media screen and(max-width: 680px) {
  .shop-bank {
    &__list {
      grid-template-columns: repeat(auto-fit, minmax(145px, 1fr));
    }
  }
}

@media screen and(max-width: 961px) {
  .shop-bank {
    padding-top: 20;
    padding-bottom: 0;

    border-radius: 10px;

    &__title {
      display: none;
    }
    &__list {
      margin-top: 0;
    }
  }
}
</style>