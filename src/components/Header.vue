<template>
  <header class="header">
    <Header-button
      :buttonText="button.text[0]"
      :buttonImageName="button.imageName[0]"
    />
    <div class="header__center">
      <Money-Counter
        :counterAmount="counter.amount[0]"
        :counterImageName="counter.imageName[0]"
        :counterName="counter.name[0]"
      />
      <Money-Counter
        :counterAmount="counter.amount[1]"
        :counterImageName="counter.imageName[1]"
        :counterName="counter.name[1]"
      />
    </div>
    <div class="header__right">
      <Header-button
        :buttonText="button.text[1]"
        :buttonImageName="button.imageName[1]"
      />
    </div>
  </header>
</template>

<script>
import HeaderButton from "./HeaderButton.vue";
import MoneyCounter from "./MoneyCounter.vue";

export default {
  name: "Header",
  components: {
    HeaderButton,
    MoneyCounter,
  },

  data() {
    return {
      button: {
        text: ["back", "home"],
        imageName: ["arrow.svg", "home.svg"],
      },

      counter: {
        amount: ["100 254", "1 254"],
        name: ["coins", "crystals"],
        imageName: ["coins.svg", "crystals.svg"],
      },
    };
  },
};
</script>

<style lang="scss" scoped>
.header {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 10;

  display: grid;
  grid-template-columns: 20% 60% 20%;
  align-items: center;

  height: 90px;
  padding: 0 40px;

  &:after {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: linear-gradient(180deg, #07050a 0%, rgba(0, 0, 0, 0) 100%);
    z-index: 2;
  }

  &__center {
    display: flex;
    justify-content: center;
    gap: 70px;
  }

  &__right {
    display: flex;
    justify-content: flex-end;
  }

  &__item {
    position: relative;
    z-index: 3;
    display: flex;
    align-items: center;

    cursor: pointer;

    &-img {
      width: 70px;
      height: 70px;

      margin-right: 10px;
    }

    &-text {
      margin-right: 20px;

      &_margin-right {
        margin-right: 40px;
      }
    }

    &-number {
      font-family: "Open Sans", sans-serif;
      font-size: 18px;
      font-weight: 700;
      color: #fff;
    }

    &-name {
      font-size: 10px;
      font-weight: 500;
      color: #b9b7ea;
      text-transform: capitalize;
    }

    &-plus {
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
}

@media screen and(max-width:960px) {
  .header {
    grid-template-columns: 50px 1fr 50px;

    height: 50px;
    padding: 0 5px;

    &::after {
      background: #242332;
    }

    &__center {
      gap: 15px;
    }
  }
}
</style>