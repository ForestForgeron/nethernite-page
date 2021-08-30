<template>
  <nav class="shop-navbar">
    <ul class="shop-navbar__list">
      <li
        class="shop-navbar__item"
        v-for="itemName in navbarItemNames"
        :key="itemName"
      >
        <a href="#" class="shop-navbar__link" v-html="itemName"></a>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: "ShopNavbar",
  components: {},
  data() {
    return {
      navbarItemNames: [
        "монстр<wbr>боксы",
        "банк",
        "наборы",
        "спец<wbr>предложения",
        "промо<wbr>коды",
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
.shop-navbar {
  padding-top: 10px;

  font-family: "Open Sans", sans-serif;
  &__list {
    display: flex;
    gap: 10px;
    justify-items: center;
  }

  &__item {
    position: relative;

    width: 190px;
    height: 55px;
  }

  &__link {
    display: flex;
    justify-content: center;
    align-items: center;

    width: 100%;
    height: 100%;

    font-size: 20px;
    font-weight: 700;
    text-transform: capitalize;

    background: #242333;
    color: #9794c6;

    border-radius: 10px 10px 0px 0px;

    transition: all 0.3s ease;

    &::after {
      content: "";
      position: absolute;
      bottom: 0;

      width: 148px;
      height: 3px;

      background: transparent;
    }

    &:hover {
      color: #fff;
    }

    &:hover:after {
      animation: linkUnderline 0.3s ease-in-out 0.2s forwards;
    }
  }
}

@keyframes linkUnderline {
  0% {
    background: transparent;
  }

  100% {
    background: linear-gradient(90deg, #f52cbf 0%, #ff7c46 100%);
  }
}

@media screen and(max-width: 1360px) {
  .shop-navbar {
    display: flex;
    justify-content: center;
    padding-top: 0;
    width: 72vw;

    background: #181723;
    &__list {
      gap: 20px;
    }

    &__item {
      width: auto;
      max-width: 90px;

      height: 50px;

      padding-right: 15px;

      &:nth-child(1) {
        padding-right: 0;
      }
    }

    &__link {
      font-size: 14px;
      text-align: center;

      background: transparent;

      border-radius: 0;

      &::after {
        width: 30px;
      }
    }
  }
}

@media screen and(max-width: 460px) {
  .shop-navbar {
    &__list {
      gap: 5px;
    }
  }
}
</style>