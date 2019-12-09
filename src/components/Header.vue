<template>
  <header id="headerId" class="header">
    <div class="container">
      <div class="header__wrap">
        <h1 class="header__title">Аккумуляторные батареи</h1>

        <div class="header__buttons">
          <svg
            aria-hidden="true"
            style="position: absolute; width: 0; height: 0; overflow: hidden;"
            version="1.1"
            xmlns="http://www.w3.org/2000/svg"
            xmlns:xlink="http://www.w3.org/1999/xlink"
          >
            <defs>
              <symbol id="icon-grid" viewBox="0 0 24 24">
                <title>Отобразить товары в виде ПЛИТОК</title>
                <path
                  d="M3 2c-0.552 0-1 0.448-1 1v7c0 0.552 0.448 1 1 1h7c0.552 0 1-0.448 1-1v-7c0-0.552-0.448-1-1-1zM4 4h5v5h-5zM14 2c-0.552 0-1 0.448-1 1v7c0 0.552 0.448 1 1 1h7c0.552 0 1-0.448 1-1v-7c0-0.552-0.448-1-1-1zM15 4h5v5h-5zM14 13c-0.552 0-1 0.448-1 1v7c0 0.552 0.448 1 1 1h7c0.552 0 1-0.448 1-1v-7c0-0.552-0.448-1-1-1zM15 15h5v5h-5zM3 13c-0.552 0-1 0.448-1 1v7c0 0.552 0.448 1 1 1h7c0.552 0 1-0.448 1-1v-7c0-0.552-0.448-1-1-1zM4 15h5v5h-5z"
                />
              </symbol>
            </defs>
          </svg>

          <svg class="header-icon header-icon__hover" @click="briefly()">
            <use xlink:href="#icon-grid" />
          </svg>

          <svg
            aria-hidden="true"
            style="position: absolute; width: 0; height: 0; overflow: hidden;"
            version="1.1"
            xmlns="http://www.w3.org/2000/svg"
            xmlns:xlink="http://www.w3.org/1999/xlink"
          >
            <defs>
              <symbol id="icon-list" viewBox="0 0 24 24">
                <title>Отобразить товары в виде СПИСКА</title>
                <path
                  d="M8 7h13c0.552 0 1-0.448 1-1s-0.448-1-1-1h-13c-0.552 0-1 0.448-1 1s0.448 1 1 1zM8 13h13c0.552 0 1-0.448 1-1s-0.448-1-1-1h-13c-0.552 0-1 0.448-1 1s0.448 1 1 1zM8 19h13c0.552 0 1-0.448 1-1s-0.448-1-1-1h-13c-0.552 0-1 0.448-1 1s0.448 1 1 1zM4 6c0-0.552-0.448-1-1-1s-1 0.448-1 1 0.448 1 1 1 1-0.448 1-1zM4 12c0-0.552-0.448-1-1-1s-1 0.448-1 1 0.448 1 1 1 1-0.448 1-1zM4 18c0-0.552-0.448-1-1-1s-1 0.448-1 1 0.448 1 1 1 1-0.448 1-1z"
                />
              </symbol>
            </defs>
          </svg>

          <svg class="header-icon header-icon__hover" @click="detailed()">
            <use xlink:href="#icon-list" />
          </svg>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header",

  data: () => ({
    isBriefly: true,
    isDetailed: false
  }),

  methods: {
    briefly: function() {
      this.isDetailed = false;
      this.isBriefly = true;

      this.$emit("is-briefly-flag", this.isBriefly, this.isDetailed);
    },

    detailed: function() {
      this.isDetailed = true;
      this.isBriefly = false;

      this.$emit("is-briefly-flag", this.isBriefly, this.isDetailed);
    }
  }
};
</script>

<style scoped lang="scss">
@import "../stylesheets/variables.scss";
@import "../stylesheets/resets.scss";

p {
  margin: 0;
}

h1 {
  font-size: 26px;
}

ul,
li {
  list-style-type: none;
  margin: 0;
  padding: 0;
}
.header {
  margin-top: 50px;
  font-family: $font-family-primary;

  &__wrap {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  &__title {
    display: block;
  }

  &__buttons {
    margin-right: 32px;
  }

  &-icon {
    display: inline-block;
    width: 20px;
    height: 20px;
    stroke-width: 0;
    stroke: currentColor;
    fill: currentColor;

    &__hover {
      margin-left: 10px;
      transition: color 0.3s ease, border-color 0.3s ease,
        background-color 0.2s ease;
      border: 1px solid $color-white;
      border-radius: 3px;
      cursor: pointer;
    }

    &__hover:hover {
      color: $color-red;
      border-color: $color-red;
    }
  }
}
</style>
