<template>
  <div class="card">
    <div class="card__frame">
      <div class="card__line">
        <div class="card__inner-line">
          <div class="card__line-coin"></div>
          <div class="card__line-text">x500</div>
        </div>
      </div>
      <div class="card__content-wrapper">
        <img
          :src="getImgSrc(cardImgSrc)"
          alt="crystals image"
          class="card__img"
        />
        <div class="card__text">
          <span class="card__number"> {{ resourcesAmount }} </span>
          <span class="card__name"> handful of coins </span>
        </div>
        <div class="card__button">
          <Card-Button />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import CardButton from "./CardButton.vue";
export default {
  name: "Card",
  components: {
    CardButton,
  },
  props: {
    cardImgSrc: {
      type: String,
      required: true,
    },
    resourcesAmount: {
      type: String,
      required: true,
    },
  },

  data() {
    return {};
  },

  methods: {
    getImgSrc(imageSrc) {
      return require("../assets/shop-img/" + imageSrc);
    },
  },
};
</script>

<style lang="scss" scoped>
.card {
  position: relative;

  width: 220px;
  height: 300px;

  background: url("../assets/shop-img/item-background.svg") center no-repeat;

  cursor: pointer;

  transition: all 0.3s ease-in-out;

  &:hover {
    transform: scale(1.1);
  }

  &__frame {
    position: absolute;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;

    background: url("../assets/shop-img/frame.svg") center no-repeat;

    &::after {
      content: "";
      position: absolute;
      top: 0;
      bottom: 0;
      left: 0;
      right: 0;

      background: linear-gradient(
        180deg,
        rgba(68, 67, 92, 0) 29.69%,
        rgba(36, 35, 51, 0) 57.29%,
        #242333 100%
      );
      border-radius: 0px 0px 15px 15px;
    }
  }

  &__line {
    position: absolute;

    width: 85px;
    height: 75px;

    background: url("../assets/shop-img/lenta-big.svg") center no-repeat;
  }

  &__inner-line {
    position: absolute;

    width: 78px;
    height: 73px;

    background: url("../assets/shop-img/lenta-small.svg") center no-repeat;
  }

  &__line-coin {
    position: absolute;
    top: 34px;
    left: 10px;

    width: 17px;
    height: 17px;

    background: url("../assets/shop-img/coin.svg") center no-repeat;
  }

  &__line-text {
    position: absolute;
    top: 17px;
    left: 23px;

    font-size: 13px;
    font-weight: 700;

    color: #fff;

    transform: rotate(-40deg);
  }

  &__content-wrapper {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  &__img {
    max-width: 150px;
    height: 120px;
    margin-top: 25px;
    margin-bottom: 10px;
  }

  &__text {
    display: flex;
    flex-direction: column;
    align-items: center;

    color: #fff;
  }

  &__number {
    font-size: 30px;
    font-weight: 700;
  }

  &__name {
    font-size: 14px;
    text-transform: capitalize;
  }

  &__button {
    position: relative;
    z-index: 5;
    margin-top: 30px;
  }
}

@media screen and(max-width: 680px) {
  .card {
    width: 125px;
    height: 170px;

    &__line {
      width: 65px;
      height: 55px;
    }

    &__inner-line {
      width: 60px;
      height: 50px;
    }

    &__line-coin {
      top: 22px;
      left: 5px;

      width: 14px;
      height: 14px;
    }

    &__line-text {
      top: 10px;
      left: 15px;

      font-size: 11px;
    }

    &__img {
      max-width: 87px;
      height: 48px;
      margin-top: 25px;
      margin-bottom: 10px;
    }

    &__number {
      font-size: 20px;
    }

    &__name {
      font-size: 11px;
    }

    &__button {
      margin-top: 15px;
    }
  }
}
</style>