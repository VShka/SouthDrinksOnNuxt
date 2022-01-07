<template>
  <div class="juice__detail">
    <div class="juice__detail-top">
      <img
        :src="require(`../assets/img/juices/${juice.image.toLowerCase()}.png`)"
        alt="Изображение сока"
        class="juice__image"
      />

      <div class="juice__info">
        <h2 class="juice__title">Сок</h2>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ChosenJuiceDetailInfo',

  props: {
    juice: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style scoped></style>
