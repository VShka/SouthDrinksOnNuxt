<template>
  <div class="juice-miniature" :data-name="juice.fruitImage" @click="$emit('chooseSlide')">
    <img
      :src="require(`../assets/img/slider-miniature/${juice.slideMiniature.toLowerCase()}.png`)"
      alt="Миниатюра сока"
      class="miniature"
    />
  </div>
</template>

<script>
export default {
  name: 'SliderJuiceMiniature',

  props: {
    juice: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style lang="scss">
.juice-miniature {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;

  width: 78px;
  height: 78px;

  background-color: #faf5e9;

  border-radius: 100px;

  cursor: pointer;

  transition: 1s;

  &:hover {
    transform: translateX(30px);
    transition: 0.5s;
  }

  &:hover::after {
    content: attr(data-name);
    position: absolute;
    left: 100px;
    bottom: 25px;
    background: #20b84f;
    border-radius: 6px;
    color: #fff;
    font-family: Rubik;
    font-size: 18px;
    padding: 3px 18px;
  }
}
</style>
