<template>
  <footer id="footerId" class="footer">
    <div class="container">
      <h2 class="footer__title">
        <img src="../../public/images/footer-bolt.png" alt="болтик" class="footer__img _left" />
        Недавно вы смотрели
        <img
          src="../../public/images/footer-bolt.png" alt="болтик" class="footer__img _right" />
      </h2>

      <ul class="footer-list">
        <FooterItem v-for="item in list" :key="item.id" :item="item" />
      </ul>
    </div>
  </footer>
</template>

<script>
import FooterItem from "./FooterItem.vue";

export default {
  name: "vFooter",

  components: {
    FooterItem
  },

  data: () => ({
    list: [
      {
        id: "0",
        img: "/images/footer-helix.png",
        title: "Масло моторное SHELL HELIX HX8 5W30 синтетика 4 л",
        price: "1 935 ₽"
      },
      {
        id: "1",
        img: "/images/footer-motul.png",
        title: "Масло моторное MOTUL 8100 ECO-LITE 5W30 синтетик...",
        price: "3 676 ₽"
      },
      {
        id: "2",
        img: "/images/footer-sonax.png",
        title: "Полироль для кузова SONAX с восковым каранда...",
        price: "560 ₽"
      },
      {
        id: "3",
        img: "/images/footer-goodrich.png",
        title: "Шина зимняя BFGOODRICH G-FORCE WINTER 2 17...",
        price: "От 2 949"
      }
    ]
  })
};
</script>

<style scoped lang="scss">
$color-gray: rgb(245, 245, 243);
$color-white: #ffffff;
$font-family-primary: "Myriad Pro Regular", "Verdana", "Arial", sans-serif;

h1,
h2,
h3,
h4,
h5,
h6,
p {
  margin: 0;
}

ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
}

.footer {
  font-family: $font-family-primary;
  // height: 300px;
  background-color: $color-gray;
  margin-top: 5px;
  padding-top: 5px;

  &__title {
    text-align: center;
    font-size: 20px;
  }

  &__img._left {
    margin: 0 5px 3px 0;
  }

  &__img._right {
    margin: 0 0 3px 5px;
  }

  &-list {
    display: flex;
    justify-content: center;
    align-items: center;
    margin-top: 20px;
  }
}
</style>
