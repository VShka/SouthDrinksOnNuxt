<template>
  <div class="juice-miniature" @click="$emit('chooseSlide')">
    <img
      :src="require(`../assets/img/juices/${juice.slideMiniature.toLowerCase()}.png`)"
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
  display: flex;
  align-items: center;
  justify-content: center;

  width: 78px;
  height: 78px;

  background-color: #faf5e9;

  border-radius: 100px;

  cursor: pointer;
}
</style>
