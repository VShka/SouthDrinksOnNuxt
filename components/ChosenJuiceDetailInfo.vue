<template>
  <div class="juice__detail">
    <div class="juice__detail-top">
      <h2 class="juice__title_mobile">{{ juice.name.toLowerCase() }}</h2>

      <img
        :src="require(`../assets/img/juices/${juice.image.toLowerCase()}.png`)"
        :alt="juice.tooltip"
        class="juice__image"
      />

      <div class="juice__info">
        <h2 class="juice__title">{{ juice.name.toLowerCase() }}</h2>

        <p v-if="juice.description" class="juice__description">{{ juice.description }}</p>

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

            <span class="juice__additional-text">Без ГМО</span>
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
        <h3 v-if="juice.composition.main" class="juice__composition-title">Состав:</h3>

        <p
          v-if="juice.composition.main"
          class="juice__composition-info juice__composition-info_main"
        >
          {{ juice.composition.main }}
        </p>

        <p v-if="juice.composition && juice.composition.additional" class="juice__composition-info">
          {{ juice.composition.additional }}
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
.juice__title_mobile {
  display: none;
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
  align-items: baseline;
  gap: 70px;

  margin-top: 70px;
}
.juice__additional-icon {
  width: 60px;
  height: 60px;
  background-size: contain;
  background-repeat: no-repeat;
  background-position: center;
  margin-bottom: 10px;

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
.juice__composition-info_main {
  margin-bottom: 20px;
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

@media (max-width: 1440px) {
  .juice__image {
    width: 370px;
  }
  .juice__fruit-image {
    width: 375px;
    height: 375px;
  }
  .juice__detail-top {
    gap: 75px;
  }
  .juice__title {
    font-size: 26px;
    line-height: 35px;
  }
  .juice__benefit {
    font-size: 20px;
  }
  .juice__macronutrients {
    width: 420px;
    gap: 75px;
    padding: 7px 0;
  }
  .juice__detail {
    width: 100%;
  }
  .juice__macronutrient-item-info {
    font-size: 20px;
    line-height: 110%;
  }
  .juice__additional {
    margin-top: 40px;
  }
  .juice__additional-icon {
    width: 50px;
    height: 50px;
  }
  .juice__additional-text {
    font-size: 18px;
    line-height: 130%;
  }
  .juice__composition-title {
    font-size: 26px;
    line-height: 16px;
    margin-bottom: 10px;
  }
  .juice__composition-info {
    font-size: 20px;
  }
  .juice__detail-bottom {
    margin: 50px 0 0;
    gap: 30px;
  }
  .juice__composition-microelement-title {
    margin-top: 45px;
  }
  .juice__microelements {
    margin-top: 20px;
  }

  .juice__detail-bottom__additional {
    margin-top: 105px;
    gap: 160px;
  }
  .juice__detail-bottom-title {
    font-size: 20px;
  }
  .juice__detail-bottom-text {
    font-size: 18px;
  }
}
@media (max-width: 1200px) {
  .juice__image {
    width: 295px;
  }
  .juice__title {
    font-size: 24px;
    line-height: 30px;
    margin-bottom: 15px;
  }
  .juice__description {
    font-size: 18px;
  }
  .juice__benefit {
    font-size: 18px;
  }
  .juice__detail-top {
    gap: 40px;
  }
  .juice__fruit-image {
    width: 300px;
    height: 300px;
  }
  .juice__detail-bottom {
    gap: 20px;
  }
  .juice__detail-bottom__additional {
    margin-top: 120px;
  }
  .juice__macronutrients {
    max-width: 100%;
    width: 100%;
  }
  .juice__macronutrient-item-title {
    font-size: 14px;
  }
  .juice__macronutrient-item-info {
    font-size: 18px;
  }
  .juice__macronutrient-inscription {
    font-size: 12px;
  }
  .juice__additional-text {
    font-size: 16px;
  }
  .juice__additional-icon {
    margin-bottom: 5px;
  }
  .juice__microelement-item {
    width: 120px;
    height: 120px;
    font-size: 16px;
  }

  .juice__composition-title {
    font-size: 24px;
  }
  .juice__composition-info {
    font-size: 18px;
  }
  .juice__composition-microelement-title {
    margin-top: 25px;
  }
  .juice__composition-microelement-title {
    font-size: 18px;
  }
  .juice__detail-bottom-title {
    font-size: 18px;
  }
  .juice__detail-bottom-text {
    font-size: 16px;
    line-height: 15px;
    margin-top: 10px;
  }
}
@media (max-width: 1023px) {
  .juice__fruit-image {
    display: none;
  }
  .juice__detail-top {
    flex-direction: column;
    gap: 0;
  }
  .juice__image {
    margin: 20px 0;
  }
  .juice__title {
    display: none;
  }
  .juice__title_mobile {
    display: block;
    font-weight: bold;
    color: #4b4961;
    font-size: 24px;
    line-height: 30px;
    margin-bottom: 0;
    margin-top: 15px;
    text-align: center;
  }
  .juice__info {
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  .juice__macronutrients {
    justify-content: center;
  }
  .juice__microelements {
    gap: 0;
    justify-content: space-evenly;
  }
  .juice__additional {
    justify-content: center;
  }
  .juice__description {
    font-size: 16px;
    line-height: 19px;
    text-align: center;
  }
  .juice__benefit {
    font-size: 16px;
    line-height: 19px;
    text-align: center;
  }
  .juice__composition {
    width: 100%;
  }
  .juice__composition-title {
    font-size: 20px;
  }
  .juice__composition-info {
    font-size: 16px;
  }
  .juice__macronutrient-inscription {
    align-self: flex-start;
  }
  .juice__additional-icon {
    width: 40px;
    height: 40px;
  }
  .juice__additional_first {
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
  }
  .juice__additional_second {
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
  }
  .juice__detail-bottom {
    margin: 30px 0 0;
  }
  .juice__detail-bottom__additional {
    margin-top: 80px;
    gap: 70px;
  }
  .juice__detail-bottom-title {
    line-height: 22px;
  }
  .juice__detail-bottom-text {
    font-size: 14px;
  }
}
@media (max-width: 767px) {
  .juice__title_mobile {
    font-size: 18px;
    line-height: 25px;
  }
  .juice__image {
    width: 200px;
  }
  .juice__macronutrient-item {
    gap: 0;
  }
  .juice__macronutrient-item-title {
    font-size: 12px;
    line-height: 18px;
  }
  .juice__macronutrient-item-info {
    font-size: 14px;
    line-height: 21px;
  }
  .juice__macronutrient-inscription {
    font-size: 10px;
  }
  .juice__additional-icon {
    width: 30px;
    height: 30px;
  }
  .juice__additional-text {
    font-size: 12px;
    line-height: 18px;
  }
  .juice__composition-title {
    font-size: 18px;
  }
  .juice__composition-info {
    line-height: 22px;
  }
  .juice__detail-bottom__additional {
    margin-top: 120px;
  }
}
@media (max-width: 425px) {
  .juice__detail-bottom {
    display: none;
  }
  .juice__detail-bottom__additional {
    margin-top: 80px;
    flex-direction: column-reverse;
    text-align: center;
    gap: 40px;
  }
  .juice__detail-bottom-title {
    padding-bottom: 10px;
    &::after {
      height: 2px;
      left: 33%;
    }
  }
}
</style>
