<template>
  <div class="juice-miniature" @click="$emit('chooseSlide')">
    <img
      :src="require(`../assets/img/slider-miniature/${juice.slideMiniature.toLowerCase()}.png`)"
      alt="Миниатюра сока"
      class="miniature"
    />
    <div class="juice__tooltip">
      <span>{{ juice.tooltip }}</span>
    </div>
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

    .juice__tooltip {
      opacity: 1;
      transform: translateX(-5px);
      transition: all 0.6s;
    }
  }
}
.juice__tooltip {
  position: absolute;
  left: 100px;
  bottom: 25px;
  opacity: 0;
  background: #20b84f;
  border-radius: 6px;
  color: #fff;
  font-family: Rubik;
  font-size: 18px;
  padding: 3px 18px;
  transition: all 0.6s;
  transform: translateX(20px);

  span {
    position: relative;

    &::before {
      position: absolute;
      top: 6px;
      left: -20px;
      content: '';
      width: 10px;
      height: 10px;
      background-color: #20b84f;
      transform: rotate(45deg);
    }
  }
}
</style>
