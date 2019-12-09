<template>
  <div class="main-item__rating">
    <p
      v-for="number in 5"
      :key="number"
      :class="['main-item__star', value >= number ? '_color-yellow' : '_color-gray']"
    >★</p>
  </div>
</template>

<script>
export default {
  name: "Rating",

  props: {
    value: {
      type: Number,
      required: true
    }
  }
};
</script>

<style lang="scss">
$color-dark-gray: rgb(82, 82, 81);
$color-yellow-star: #f70;

._color-yellow {
  color: $color-yellow-star;
}

._color-gray {
  color: $color-dark-gray;
}

.main-item__rating {
  display: flex;
  
}

.main-item__star {
  font-size: 10px;
}
</style>