<template>
  <main id="mainId" class="main">
    <ul class="main-list">
      <MainItem
        v-for="item in list.slice(0, showIndex)"
        :key="item.id"
        :item="item"
        class="main-item-component"
      />
    </ul>

    <div class="main-footer">
      <div class="main-page-number">
        <ul class="main-page-number-list">
          <li class="main-page-number-item">
            <button class="main-page-number-item__button-back _btn-disable">
              <span class="_btn-big">&lt;</span>
            </button>
          </li>
          <li class="main-page-number-item">
            <button class="main-page-number-item__button _btn-active">1</button>
          </li>
          <li class="main-page-number-item">
            <button class="main-page-number-item__button">2</button>
          </li>
          <li class="main-page-number-item">
            <button class="main-page-number-item__button">3</button>
          </li>
          <li class="main-page-number-item">
            <button class="main-page-number-item__button">4</button>
          </li>
          <li class="main-page-number-item">
            <button class="main-page-number-item__button">5</button>
          </li>
          <li class="main-page-number-item">
            <button class="main-page-number-item__button-next">
              <span class="_btn-big">&gt;</span>
            </button>
          </li>
        </ul>
      </div>

      <select v-model="showIndex" class="main-select">
        <option class="main-select__option" value="3">3</option>
        <option class="main-select__option" value="6">6</option>
        <option class="main-select__option" value="9">9</option>
        <option class="main-select__option" value="12">12</option>
      </select>
    </div>
  </main>
</template>

<script>
import MainItem from "./MainItem.vue";

export default {
  name: "Maim",

  components: {
    MainItem
  },

  data: () => ({
    list: [
      {
        id: "0",
        img: "/images/main-1-1.png",
        rating: "0",
        title: "Аккумулятор VARTA ASIA BLUE DYNAMIC D47 60 Ач 540А О/П",
        description:
          "Подробное описание товара. Подробное описание товара. Подробное описание товара. Подробное описание товара. Подробное описание товара. Подробное описание товара.",
        price: "5 460 ₽"
      },
      {
        id: "1",
        img: "/images/main-1-2.png",
        rating: "0",
        title: "Аккумулятор VARTA SILVER DYNAMIC C30 54 Ач 530А О/П",
        description:
          "Подробное описание товара. Подробное описание товара. Подробное описание товара. Подробное описание товара. Подробное описание товара. Подробное описание товара.",
        price: "6 416 ₽"
      },
      {
        id: "2",
        img: "/images/main-1-3.png",
        rating: "1",
        title: "Аккумулятор BOSCH SILVER S5013 100 Ач 830А О/П",
        description:
          "Подробное описание товара. Подробное описание товара. Подробное описание товара. Подробное описание товара. Подробное описание товара. Подробное описание товара.",
        price: "10 440 ₽"
      },
      {
        id: "3",
        img: "/images/main-2-1.png",
        rating: "5",
        title: "Аккумулятор BOSCH ASIA SILVER S4028 95 Ач 830А О/П",
        description:
          "Подробное описание товара. Подробное описание товара. Подробное описание товара. Подробное описание товара. Подробное описание товара. Подробное описание товара.",
        price: "9 000 ₽"
      },
      {
        id: "4",
        img: "/images/main-2-2.png",
        rating: "3",
        title: "Аккумулятор BOSCH ASIA SILVER S4025 60 Ач 540А",
        description:
          "Подробное описание товара. Подробное описание товара. Подробное описание товара. Подробное описание товара. Подробное описание товара. Подробное описание товара.",
        price: "5 941 ₽"
      },
      {
        id: "5",
        img: "/images/main-2-3.png",
        rating: "0",
        title: "Аккумулятор BOSCH SILVER S4013 95 Ач 800А О/П",
        description:
          "Подробное описание товара. Подробное описание товара. Подробное описание товара. Подробное описание товара. Подробное описание товара. Подробное описание товара.",
        price: "10 104 ₽"
      },
      {
        id: "6",
        img: "/images/main-1-1.png",
        rating: "0",
        title: "Аккумулятор VARTA ASIA BLUE DYNAMIC D47 60 Ач 540А О/П",
        description:
          "Подробное описание товара. Подробное описание товара. Подробное описание товара. Подробное описание товара. Подробное описание товара. Подробное описание товара.",
        price: "5 460 ₽"
      },
      {
        id: "7",
        img: "/images/main-1-2.png",
        rating: "0",
        title: "Аккумулятор VARTA SILVER DYNAMIC C30 54 Ач 530А О/П",
        description:
          "Подробное описание товара. Подробное описание товара. Подробное описание товара. Подробное описание товара. Подробное описание товара. Подробное описание товара.",
        price: "6 416 ₽"
      },
      {
        id: "8",
        img: "/images/main-1-3.png",
        rating: "1",
        title: "Аккумулятор BOSCH SILVER S5013 100 Ач 830А О/П",
        description:
          "Подробное описание товара. Подробное описание товара. Подробное описание товара. Подробное описание товара. Подробное описание товара. Подробное описание товара.",
        price: "10 440 ₽"
      },
      {
        id: "9",
        img: "/images/main-2-1.png",
        rating: "5",
        title: "Аккумулятор BOSCH ASIA SILVER S4028 95 Ач 830А О/П",
        description:
          "Подробное описание товара. Подробное описание товара. Подробное описание товара. Подробное описание товара. Подробное описание товара. Подробное описание товара.",
        price: "9 000 ₽"
      },
      {
        id: "10",
        img: "/images/main-2-2.png",
        rating: "3",
        title: "Аккумулятор BOSCH ASIA SILVER S4025 60 Ач 540А",
        description:
          "Подробное описание товара. Подробное описание товара. Подробное описание товара. Подробное описание товара. Подробное описание товара. Подробное описание товара.",
        price: "5 941 ₽"
      },
      {
        id: "11",
        img: "/images/main-2-3.png",
        rating: "0",
        title: "Аккумулятор BOSCH SILVER S4013 95 Ач 800А О/П",
        description:
          "Подробное описание товара. Подробное описание товара. Подробное описание товара. Подробное описание товара. Подробное описание товара. Подробное описание товара.",
        price: "10 104 ₽"
      }
    ],

    showIndex: 3
  }),

  methods: {
    test: function() {
      this.testBool = !this.testBool;
    }
  }
};
</script>

<style lang="scss">
@import "../stylesheets/variables.scss";
@import "../stylesheets/resets.scss";

%button-page-number {
  position: relative;
  width: 30px;
  height: 30px;
  font-family: $font-family-primary;
  margin: 0 auto;
  padding-top: 1px;
  border: none;
  border-radius: 15px;
  transition: background-color 0.1s ease, border-color 0.3s ease;
  font-size: 12px;
  font-weight: 700;
  line-height: 1;
  background: $color-white;
}

%button-page-number-hover {
  background-color: $color-yellow;
  cursor: pointer;
}

ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
}

.main {
  font-family: $font-family-primary;
  width: 825px;

  &-list {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
    // margin-top: 20px;
  }

  &-item-component {
    margin: 10px;
  }

  &-footer {
    display: flex;
    justify-content: space-between;
    margin-top: 40px;
    padding-right: 32px;
    padding-left: 32px;
  }

  &-page-number {
    display: block;
    width: 220px;

    &-list {
      display: flex;
      justify-content: space-between;
    }

    &-item {
      display: block;

      &__button,
      &__button-next,
      &__button-back {
        @extend %button-page-number;
      }

      &__button:focus,
      &__button:hover {
        @extend %button-page-number-hover;
      }

      &__button-next:focus,
      &__button-back:focus,
      &__button-next:hover,
      &__button-back:hover {
        border: 2px solid $color-yellow;
        transform: scale(1.1);
      }
    }
  }
}
._btn-active {
  background: $color-yellow;
}

._btn-disable {
  color: $color-gray;
}

._btn-big {
  font-size: 18px;
}
</style>