<template>
  <div class="juice__detail">
    <div class="juice__detail-top">
      <img
        :src="require(`../assets/img/juices/${juice.image.toLowerCase()}.png`)"
        :alt="juice.tooltip"
        class="juice__image"
        @mousedown.prevent.stop
      />

      <div class="juice__info">
        <h2 class="juice__title">{{ juice.name.toLowerCase() }}</h2>

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

        <h4 class="juice__composition-microelement-title">
          Один стакан напитка (250мл) содержит витамины:
        </h4>

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

    <div class="juice__detail-bottom__additional">
      <div class="juice__detail-bottom-container">
        <p class="juice__detail-bottom-title">Срок годности</p>

        <p class="juice__detail-bottom-text">12 месяцев со дня розлива указанного на этикетке</p>
      </div>

      <div class="juice__detail-bottom-container">
        <p class="juice__detail-bottom-title">Энергетическая ценность</p>

        <p class="juice__detail-bottom-text">
          {{ juice.energyValue }}
        </p>
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

<style lang="scss" scoped>
.juice__detail {
  width: 1450px;
}
.juice__detail-top {
  display: flex;
  align-items: center;
  gap: 145px;
}
.juice__title {
  font-weight: bold;
  font-size: 36px;
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
  gap: 90px;

  max-width: 460px;

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
  gap: 115px;

  margin: 140px 0 100px;
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
  border-radius: 0 90px 0 90px;
}

.juice__detail-bottom__additional {
  display: flex;
  gap: 230px;
  margin-top: 163px;
}
.juice__detail-bottom-container {
  max-width: 580px;
}
.juice__detail-bottom-title {
  position: relative;
  font-family: Montserrat Alternates;
  font-style: normal;
  font-weight: bold;
  font-size: 24px;
  line-height: 29px;

  color: #484848;

  padding-bottom: 13px;

  &:after {
    position: absolute;
    bottom: 0;
    left: 0;
    content: '';
    width: 123px;
    height: 3px;
    background: linear-gradient(269.21deg, #ffd25a 0.49%, #ffc52b 100%);
  }
}
.juice__detail-bottom-text {
  font-family: Rubik;
  font-style: normal;
  font-weight: normal;
  font-size: 24px;
  line-height: 28px;

  color: #a6a6a6;

  margin-top: 14px;
}
</style>
