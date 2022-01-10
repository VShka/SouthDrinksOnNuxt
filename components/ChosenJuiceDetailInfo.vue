<template>
  <div class="juice__detail">
    <div class="juice__detail-top">
      <img
        :src="require(`../assets/img/juices/${juice.image.toLowerCase()}.png`)"
        alt="Изображение сока"
        class="juice__image"
      />

      <div class="juice__info">
        <h2 class="juice__title">{{ juice.name }}</h2>

        <p class="juice__description">{{ juice.description }}</p>

        <p class="juice__benefit">{{ juice.benefit }}</p>

        <ul class="juice__macronutrients">
          <li
            v-for="item in juice.macronutrients"
            :key="item.name"
            class="juice__macronutrient-item"
          >
            <p class="juice__macronutrient-item-title">{{ item.name }}</p>

            <p class="juice__macronutrient-item-info">{{ item.value }}</p>
          </li>
        </ul>

        <span class="juice__macronutrient-inscription">На 100 грамм продукта</span>

        <div class="juice__additional">
          <div class="juice__additional_first">
            <div class="juice__additional-icon juice__additional-icon_first"></div>

            <span class="juice__additional-text">
              Без красителей,<br />
              консервантов и ГМО
            </span>
          </div>

          <div class="juice__additional_second">
            <div class="juice__additional-icon juice__additional-icon_second"></div>

            <span class="juice__additional-text">
              Содержит микроэлементы <br />
              и антиоксиданты
            </span>
          </div>
        </div>
      </div>
    </div>

    <div class="juice__detail-bottom">
      <div class="juice__composition">
        <h3 class="juice__composition-title">Состав</h3>

        <p class="juice__composition-info">
          {{ juice.composition }}
        </p>

        <h4 class="juice__composition-microelement-title">Один стакан напитка (250мл) содержит:</h4>

        <ul class="juice__microelements">
          <li
            v-for="item in juice.microelements"
            :key="item.element"
            class="juice__microelement-item"
          >
            {{ item.element }}
          </li>
        </ul>
      </div>

      <img
        :src="require(`../assets/img/fruits/${juice.fruitImage.toLowerCase()}.png`)"
        alt="Изображение сока"
        class="juice__fruit-image"
      />
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

<style lang="scss" scoped>
.juice__detail-top {
  display: flex;
}
.juice__title {
  font-weight: bold;
  font-size: 48px;
  line-height: 59px;
  color: #4b4961;

  margin-bottom: 24px;
}
.juice__description {
  margin-bottom: 30px;
}
.juice__description,
.juice__benefit {
  font-family: Raleway;
  font-style: normal;
  font-weight: normal;
  font-size: 22px;
  line-height: 26px;

  color: #95979b;
}
.juice__macronutrients {
  display: flex;
  gap: 85px;

  max-width: 580px;

  border-top: 1px solid #dadada;
  border-bottom: 1px solid #dadada;

  margin-top: 50px;
  padding: 14px 0;
}
.juice__macronutrient-item {
  display: flex;
  flex-direction: column;
  gap: 5px;
}
.juice__macronutrient-item-title {
  font-family: Raleway;
  font-style: normal;
  font-weight: normal;
  font-size: 18px;
  line-height: 150%;
  color: #95979b;
}
.juice__macronutrient-item-info {
  font-family: Raleway;
  font-style: normal;
  font-weight: bold;
  font-size: 24px;
  line-height: 150%;
  background-color: #ffd25a;
  background-image: linear-gradient(#ffd25a, #ffc52b);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
.juice__macronutrient-inscription {
  font-family: Rubik;
  font-style: normal;
  font-weight: normal;
  font-size: 14px;
  line-height: 150%;
  color: #a4a4a4;
}
.juice__additional {
  display: flex;
  align-items: center;
  gap: 70px;

  margin-top: 70px;
}
.juice__additional-icon {
  width: 60px;
  height: 60px;
  background-size: contain;
  background-repeat: no-repeat;
  background-position: center;

  &_first {
    background-image: url('~/assets/img/additional_first.svg');
  }
  &_second {
    background-image: url('~/assets/img/additional_second.svg');
  }
}
.juice__additional-text {
  font-family: Rubik;
  font-style: normal;
  font-weight: normal;
  font-size: 24px;
  line-height: 150%;
  color: #4b4961;
}

.juice__detail-bottom {
  display: flex;
  position: relative;

  margin: 180px 0 100px;
}
.juice__composition-title {
  font-weight: bold;
  font-size: 48px;
  line-height: 59px;
  color: #484848;

  margin-bottom: 30px;
}
.juice__composition-info {
  font-family: Rubik;
  font-style: normal;
  font-weight: normal;
  font-size: 24px;
  line-height: 28px;
  color: #a6a6a6;
}
.juice__composition-microelement-title {
  font-family: Raleway;
  font-style: normal;
  font-weight: bold;
  font-size: 20px;
  line-height: 23px;
  color: #484848;

  margin-top: 110px;
}
.juice__microelements {
  display: flex;
  gap: 70px;

  margin-top: 40px;
}
.juice__microelement-item {
  width: 135px;
  height: 132px;

  display: flex;
  align-items: center;
  justify-content: center;

  font-family: Rubik;
  font-style: normal;
  font-weight: normal;
  font-size: 18px;
  line-height: 21px;
  text-align: center;
  color: #4b4961;

  border: 2px solid #ffd25a;
  border-radius: 57px;
}
.juice__fruit-image {
  position: absolute;
  top: -10px;
  right: 290px;
}
</style>
