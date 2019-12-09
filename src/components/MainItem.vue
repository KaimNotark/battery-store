<template>
  <li class="main-item" :class="{ '_main-item-detailed': this.$parent.$parent.isDetailed }">
    <img
      :src="item.img"
      :alt="item.title"
      class="main-item__img"
      :class="{ '_main-item-img-detailed': this.$parent.$parent.isDetailed }"
    />
    <div
      class="main-item__raiting-content-wrap"
      :class="{ '_main-item__raiting-content-wrap-detailed': this.$parent.$parent.isDetailed }"
    >
      <Rating 
      :value="item.rating" 
      class="main-item__raiting-component"
      :class="{ '_main-item__raiting-component-detailed': this.$parent.$parent.isDetailed }"
       />

      <p class="main-item__content">{{ item.title }}</p>
      <p
        class="main-item__description"
        :class="{ '_main-item__description-detailed': !this.$parent.$parent.isDetailed }"
      >{{ item.description }}</p>
    </div>

    <div class="main-item__wrap">
      <p class="main-item__price">{{ item.price }}</p>
      <button class="main-item__btn-basket" @click="detailedList">В корзину</button>
      <button class="main-item__btn-compare">
        <img
          class="main-item__btn-img"
          src="../../public/images/main-btn-compare.png"
          alt="Сравнить"
        />
        Сравнить
      </button>
      <p class="main-item__in-stock">&#10004; В наличии</p>
    </div>
  </li>
</template>

<script>
import Rating from "./Rating.vue";

export default {
  name: "MainItem",

  components: {
    Rating
  },

  props: {
    item: {
      type: Object,
      required: true
    },

    isBriefly: {
      type: Boolean,
      required: true
    },

    isDetailed: {
      type: Boolean,
      required: true
    }
  },

  data: () => ({
    isBrieflyItem: true
  }),

  methods: {
    detailedList: function() {
      this.isBrieflyItem = this.$parent.$parent.isBriefly;
      console.log("this.isBrieflyItem = " + this.isBrieflyItem);
      console.log("isBriefly = " + this.$parent.$parent.isBriefly);
    }
  }
};
</script>

<style lang="scss">
@import "../stylesheets/variables.scss";
@import "../stylesheets/resets.scss";

%button-basket {
  position: relative;
  width: 100px;
  height: 35px;
  font-family: $font-family-primary;
  padding-top: 1px;
  border: 1px solid $color-yellow;
  border-radius: 4px;
  transition: background-color 0.1s ease, border-color 0.3s ease;
  font-size: 12px;
  font-weight: 700;
  line-height: 1;
  // color: $color-dark-gray;
  // opacity: 0.8;
  background-color: $color-yellow;
}

%button-basket-hover {
  background-color: $color-white;
  border-color: $color-red;
  color: $color-red;
  text-decoration: none;
  cursor: pointer;
  // opacity: 1;
  transform: scale(1.05);
}

%button-compare {
  position: relative;
  width: 100px;
  height: 35px;
  font-family: $font-family-primary;
  padding-top: 1px;
  border: 1px solid $color-white;
  border-radius: 4px;
  transition: background-color 0.1s ease, border-color 0.3s ease;
  font-size: 12px;
  font-weight: 700;
  line-height: 1;
  // color: $color-dark-gray;
  opacity: 0.5;
  background: $color-white;
}

%button-compare-hover {
  // background-color: $color-white;
  border-color: $color-yellow;
  // color: $color-red;
  text-decoration: none;
  cursor: pointer;
  opacity: 1;
  transform: scale(1.05);
}

p {
  margin: 0;
}

li {
  list-style-type: none;
  margin: 0;
  padding: 0;
}

.main-item {
  width: 240px;
  height: 275px;
  display: block;
  padding: 10px;
  border: 1px solid $color-gray;

  &__img {
    position: relative;
    left: 50%;
    transform: translateX(-50%);
    margin-top: 20px;
  }

  &__raiting-component {
    margin-top: 20px;
  }

  &__content {
    // width: 80%;
    margin: 5px 0px 15px 0px;
    font-size: 11px;
    text-align: left;
  }

  &__description {
    font-size: 11px;
    text-align: left;
  }

  &__wrap {
    display: flex;
    flex-wrap: wrap;
    width: 240px;
    justify-content: space-between;
  }

  &__price {
    display: block;
    width: 100px;
    height: 22px;
    position: relative;
    // margin-left: 10%;
    font-size: 16px;
    font-weight: bolder;
    text-align: left;
    z-index: 1;
    margin-top: 12px;
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

  &__btn-basket {
    @extend %button-basket;
    margin: 0 auto;
  }
  &__btn-basket:focus,
  &__btn-basket:hover {
    @extend %button-basket-hover;
  }

  &__btn-compare {
    @extend %button-compare;
    margin-top: 5px;
  }
  &__btn-compare:focus,
  &__btn-compare:hover {
    @extend %button-compare-hover;
  }

  &__in-stock {
    display: block;
    font-size: 12px;
    color: $color-green;
    width: 100px;
    height: 35px;
    padding-top: 20px;
    margin-right: 30px;
    text-align: right;
  }
}

._main-item-detailed {
  width: 800px;
  height: 150px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
._main-item-img-detailed {
  position: relative;
  left: 50px;
  margin: 0;
}
._main-item__raiting-content-wrap-detailed {
  width: 50%;
}
._main-item__description-detailed {
  display: none;
}
._main-item__raiting-component-detailed {
  margin-top: 0;
}
</style>