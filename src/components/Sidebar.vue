<template>
  <div class="container-sidebar">
    <button type="button" class="sidebar-button" @click="uncheck()">
      <span class="_cross">&#10006;</span> &nbsp; Сбросить всё
    </button>

    <div class="accordion" id="accordion">
      <div class="accordion-item">
        <h3 class="accordion-item-head" v-on:click="accordion">Категория</h3>
        <div class="accordion-item-body">
          <p class="aside-item__content">
            <label class="aside-item__checkbox">
              <input type="checkbox" class="aside-item__checkbox-input" id="checked" />
              <span class="aside-item__checkbox-mark"></span>
              <span class="aside-item__checkbox-content">Аккумуляторные батареи (119)</span>
            </label>
          </p>
        </div>
      </div>

      <div class="accordion-item">
        <h3 class="accordion-item-head" v-on:click="accordion">Бренд</h3>
        <div class="accordion-item-body">
          <p class="aside-item__content">
            <label class="aside-item__checkbox">
              <input type="checkbox" class="aside-item__checkbox-input" id="checked" />
              <span class="aside-item__checkbox-mark"></span>
              <span class="aside-item__checkbox-content">BOSH (69)</span>
            </label>
          </p>
          <p class="aside-item__content">
            <label class="aside-item__checkbox">
              <input type="checkbox" class="aside-item__checkbox-input" id="checked" />
              <span class="aside-item__checkbox-mark"></span>
              <span class="aside-item__checkbox-content">VARTA (50)</span>
            </label>
          </p>
        </div>
      </div>

      <div class="accordion-item">
        <h3 class="accordion-item-head" v-on:click="accordion">Полярность</h3>
        <div class="accordion-item-body">
          <p class="aside-item__content">
            <label class="aside-item__checkbox">
              <input type="checkbox" class="aside-item__checkbox-input" id="checked" />
              <span class="aside-item__checkbox-mark"></span>
              <span class="aside-item__checkbox-content">Обратная (О/П)</span>
            </label>
          </p>
          <p class="aside-item__content">
            <label class="aside-item__checkbox">
              <input type="checkbox" class="aside-item__checkbox-input" id="checked" />
              <span class="aside-item__checkbox-mark"></span>
              <span class="aside-item__checkbox-content">Прямая (П/П)</span>
            </label>
          </p>
        </div>
      </div>

      <div class="accordion-item">
        <h3 class="accordion-item-head" v-on:click="accordion">Длина</h3>
        <div class="accordion-item-body">
          <p class="aside-item__content">
            <label class="aside-item__checkbox">
              <input type="checkbox" class="aside-item__checkbox-input" id="checked" />
              <span class="aside-item__checkbox-mark"></span>
              <span class="aside-item__checkbox-content">30 см</span>
            </label>
          </p>
          <p class="aside-item__content">
            <label class="aside-item__checkbox">
              <input type="checkbox" class="aside-item__checkbox-input" id="checked" />
              <span class="aside-item__checkbox-mark"></span>
              <span class="aside-item__checkbox-content">40 см</span>
            </label>
          </p>
          <p class="aside-item__content">
            <label class="aside-item__checkbox">
              <input type="checkbox" class="aside-item__checkbox-input" id="checked" />
              <span class="aside-item__checkbox-mark"></span>
              <span class="aside-item__checkbox-content">50 см</span>
            </label>
          </p>
          <p class="aside-item__content">
            <label class="aside-item__checkbox">
              <input type="checkbox" class="aside-item__checkbox-input" id="checked" />
              <span class="aside-item__checkbox-mark"></span>
              <span class="aside-item__checkbox-content">60 см</span>
            </label>
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Sidebar",

  data: () => ({
    inputs: 0
  }),

  methods: {
    accordion: function(event) {
      //Раскомментировать, если нужно, чтобы закрывались остальные пункты при открытии текущего
      // 	var matches = document.querySelectorAll('.accordion-item-head');
      //  	for(var i = 0; i < matches.length; i++) {
      //  		matches[i].classList.remove('active');
      //	 }

      event.target.classList.toggle("active");
    },

    uncheck: function() {
      this.inputs = document.querySelectorAll("#checked");
      
      // for (let i = 0; i < this.inputs.length; i++) {
      //   if (this.inputs[i].checked)
      //     this.inputs[i].checked = !this.inputs[i].checked;
      // }

      for (let inputChecked of this.inputs) {
        if (inputChecked.checked) inputChecked.checked = !inputChecked.checked;
      }
    }
  }
};
</script>

<style lang="scss" scoped>
@import "../stylesheets/variables.scss";
@import "../stylesheets/resets.scss";

%button-reset {
  position: relative;
  width: 275px;
  height: 35px;
  font-family: $font-family-primary;
  margin: 0 auto;
  padding-top: 1px;
  border: 1px solid $color-gray;
  border-radius: 4px;
  transition: background-color 0.1s ease, border-color 0.3s ease;
  font-size: 12px;
  font-weight: 700;
  line-height: 1;
  color: $color-dark-gray;
  opacity: 0.8;
  background: $color-gray;
}

%button-reset-hover {
  background-color: $color-dark-gray;
  border-color: $color-dark-gray;
  color: $color-white;
  text-decoration: none;
  cursor: pointer;
  opacity: 1;
}

.container-sidebar {
}

.sidebar {
  &-button {
    @extend %button-reset;
  }

  &-button:focus,
  &-button:hover {
    @extend %button-reset-hover;
  }
}
._cross {
  font-size: 16px;
}

.accordion {
  margin-top: 10px;

  &-item {
    position: relative;

    &-head {
      width: 275px;
      font-family: $font-family-primary;
      font-size: 12px;
      font-weight: 700;
      line-height: 1;
      color: $color-dark-gray;
      background-color: $color-white;
      cursor: pointer;
      padding: 10px;
      border: 1px solid $color-gray;
    }

    &-head:after {
      content: " > ";
      display: block;
      font-size: 5px;
      height: 18px;
      position: absolute;
      right: 30px;
      transform: rotate(90deg) scaleY(2);
      top: 8px;
    }

    &-head.active:after {
      content: " < ";
    }

    &-body {
      display: none;
      width: 275px;
      font-family: $font-family-primary;
      font-size: 12px;
      font-weight: 700;
      line-height: 1;
      border: 1px solid $color-gray;
      border-top: none;
      padding: 10px;
    }
    &-head.active + .accordion-item-body {
      display: block !important;
    }
    &-head.active {
      border-bottom: none;
    }
  }
}

.aside-item__content {
  color: black;
  font-size: 12px;
  line-height: 20px;
  padding: 0 20px;
  margin-bottom: 10px;
}

// --- checkbox ---

.aside-item__checkbox {
  cursor: pointer;
  padding: 0;
  user-select: none;
}
.aside-item__checkbox-input {
  position: absolute;
  visibility: hidden;
}
.aside-item__checkbox-mark {
  display: inline-block;
  position: relative;
  width: 20px;
  height: 20px;
  border: 0.05em solid gray;
  vertical-align: middle;
  margin-right: 0.2em;
  border-radius: 0.1em;
}
.aside-item__checkbox-content {
  display: block;
  width: 140px;
  margin-left: 30px;
  margin-top: -20px;
  font-family: $font-family-primary;
  font-size: 12px;
  font-weight: bold;
}
.aside-item__checkbox-input:checked + .aside-item__checkbox-mark {
  &::after {
    content: "";
    position: absolute;
    left: 7px;
    top: -4px;
    width: 12px;
    height: 17px;
    transform: rotate(45deg);
    border: 3px solid $color-green;
    border-top-color: transparent;
    border-left-color: transparent;
  }
}
</style>