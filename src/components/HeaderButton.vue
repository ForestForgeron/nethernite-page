<template>
  <button class="header-button">
    <img
      :src="getImgUrl(buttonImageName)"
      alt="back arrow"
      class="header-button__icon"
    />
    <span class="header-button__text">{{ buttonText }}</span>
  </button>
</template>

<script>
export default {
  name: "HeaderButton",
  components: {},
  props: {
    buttonText: {
      type: String,
      required: true,
    },
    buttonImageName: {
      type: String,
      required: true,
    },
  },

  data() {
    return {};
  },

  methods: {
    getImgUrl(imageName) {
      return require("../assets/header-img/" + imageName);
    },
  },
};
</script>

<style lang="scss" scoped>
.header-button {
  position: relative;
  z-index: 3;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 15px;

  width: 140px;
  height: 55px;

  background: transparent;

  border: 2px #9794c622 solid;
  border-radius: 50px;

  &__text {
    color: #fff;
    font-size: 14px;
    font-weight: 700;

    text-transform: uppercase;
  }

  &:hover {
    background-color: lighten($color: #9794c622, $amount: 1);
    border-color: #9794c6;
  }
}
@media screen and(max-width:960px) {
  .header-button {
    width: 45px;
    height: 45px;
    border: transparent;

    &__text {
      display: none;
    }
  }
}
</style>