<template>
  <li class="footer-item">
    <img :src="item.img" :alt="item.title" class="footer-item__img" />
    <p class="footer-item__description">{{ item.title }}</p>
    <p class="footer-item__price">{{ item.price }}</p>
  </li>
</template>

<script>
export default {
  name: "FooterItem",

  props: {
    item: {
      type: Object,
      required: true
    }
  }
};
</script>

<style lang="scss">
$color-white: #ffffff;
$color-yellow: #ffd900;

.footer {
  &-item {
    display: block;
    width: 160px;
    height: 250px;
    background-color: $color-white;
    margin: 5px;

    &__img {
      position: relative;
      left: 50%;
      transform: translateX(-50%);
      margin-top: 30px;
    }

    &__description {
      width: 80%;
      margin: 20px 10%;
      font-size: 11px;
      text-align: left;
    }

    &__price {
      display: block;
      width: 100px;
      height: 22px;
      position: relative;
      margin-left: 10%;
      font-size: 16px;
      font-weight: bolder;
      text-align: left;
      z-index: 1;
    }

    &__price::before {
      content: "";
      position: absolute;
      bottom: 0px;
      width: 80%;
      height: 10px;
      background-color: $color-yellow;
      z-index: -1;
    }
  }
}
</style>