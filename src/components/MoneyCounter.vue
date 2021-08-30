<template>
  <div class="money-counter">
    <img
      :src="getImgUrl(counterImageName)"
      alt="golden coins"
      class="money-counter__img"
    />
    <div
      class="money-counter__text"
      :class="lol ? 'money-counter__text_margin-right' : ''"
    >
      <p class="money-counter__number">{{ counterAmount }}</p>
      <p class="money-counter__name">{{ counterName }}</p>
    </div>
    <div class="money-counter__plus">+</div>
  </div>
</template>

<script>
export default {
  name: "MoneyCounter",
  props: {
    counterAmount: {
      type: String,
      required: true,
    },
    counterImageName: {
      type: String,
      required: true,
    },
    counterName: {
      type: String,
      required: true,
    },
  },
  data() {
    return {
      lol: this.counterName == "crystals",
    };
  },

  methods: {
    getImgUrl(imageName) {
      return require("../assets/header-img/" + imageName);
    },
  },

  computed: {
    counterNameClasses() {
      return {
        "money-counter__text": true,
        "money-counter__text_margin-right": this.counterName == "crystlas",
      };
    },
  },
};
</script>

<style lang="scss" scoped>
.money-counter {
  position: relative;
  z-index: 3;
  display: flex;
  align-items: center;

  cursor: pointer;

  transition: all 0.3s ease-in-out;

  &:hover {
    transform: scale(1.03);
  }

  &__img {
    width: 70px;
    height: 70px;

    margin-right: 10px;
  }

  &__text {
    margin-right: 20px;

    &_margin-right {
      margin-right: 40px;
    }
  }

  &__number {
    font-family: "Open Sans", sans-serif;
    font-size: 18px;
    font-weight: 700;
    color: #fff;
  }

  &__name {
    font-size: 10px;
    font-weight: 500;
    color: #b9b7ea;
    text-transform: capitalize;
  }

  &__plus {
    display: flex;
    justify-content: center;
    align-items: center;

    width: 25px;
    height: 25px;
    margin-bottom: 10px;

    font-size: 25px;

    color: #fff;
    background: linear-gradient(90deg, #30c325 9.09%, #2c812a 100%);

    border: 1px solid #21cc14;
    border-radius: 5px;

    transform: rotate(-90deg);
  }
}

@media screen and(max-width:960px) {
  .money-counter {
    &::after {
      content: "";
      position: absolute;
      top: 5px;
      bottom: 5px;
      left: 5px;
      right: 5px;

      background: #0d0b0f;
      border-radius: 100px 0px 0px 100px;
    }

    &__img {
      position: relative;
      z-index: 5;
      width: 30px;
      height: 30px;
      margin-right: 0;
    }

    &__text {
      position: relative;
      z-index: 5;

      margin-right: 15px;

      &_margin-right {
        margin-right: 25px;
      }
    }

    &__number {
      font-size: 13px;
    }

    &__name {
      display: none;
    }

    &__plus {
      position: relative;
      z-index: 5;

      width: 20px;
      height: 20px;
      margin-bottom: 0;
    }
  }
}
</style>