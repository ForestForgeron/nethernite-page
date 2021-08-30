<template>
  <button class="shop-button">
    <span class="shop-button__text"> купить </span>
    <img
      src="../assets/shop-img/dollar.svg"
      alt="dollar icon"
      class="shop-button__img"
    />
    <span class="shop-button__number"> 10 </span>
  </button>
</template>

<script>
export default {
  name: "CardButton",
};
</script>

<style lang="scss" scoped>
.shop-button {
  position: relative;

  display: flex;
  justify-content: center;
  align-items: center;

  width: 155px;
  height: 50px;
  padding: 15px 30px;

  font-family: "Roboto", Arial, sans-serif;
  font-size: 14px;
  font-weight: 700;

  background: linear-gradient(90deg, #242333 0%, #3c3b53 100%);
  border: 2px solid transparent;
  background-clip: padding-box;

  color: #fff;

  border-radius: 146px;

  &:after {
    content: "";
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    z-index: -1;

    margin: -2px;

    border-radius: inherit;
    background: linear-gradient(90deg, #682fbd 0%, #cb4cbc 100%);

    transition: all 0.3s ease-in-out;
  }

  &:hover {
    transform: scale(1.1);
  }

  &__text {
    margin-right: 20px;

    text-transform: capitalize;
  }

  &__img {
    margin-right: 5px;
  }
}

@media screen and(max-width: 680px) {
  .shop-button {
    width: 100px;
    height: 28px;
    padding: 5px 10px;

    font-size: 11px;

    background: linear-gradient(90deg, #682fbd 0%, #cb4cbc 100%);
  }
}
</style>