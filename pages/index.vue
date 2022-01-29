<template>
  <main class="container">
    <section class="header">
      <div class="header__bg"></div>
      <div class="header__leaflet_1"></div>
      <div class="header__leaflet_2"></div>
      <div class="header__leaflet_3"></div>
      <div class="header__leaflet_4"></div>
      <div class="header__leaflet_5"></div>
      <div class="header__bg-juice"></div>

      <h1 class="header__title">
        Все витамины Кубани <br />
        в каждой упаковке!
      </h1>

      <p class="header__description">
        Наша компания производит и реализует оптом и в розницу соки, натуральные напитки из
        сухофруктов, безалкогольную и газированную продукцию.
      </p>

      <a class="header__button" href="#products">Смотреть продукцию</a>
    </section>

    <section class="guarantee">
      <div class="guarantee__some-bg"></div>

      <h2 class="guarantee__title">Годы опыта — гарантии качества</h2>

      <hooper
        style="height: 889px"
        :wheel-control="false"
        :auto-play="true"
        :play-speed="10000"
        :transition="2000"
      >
        <slide>
          <div class="guarantee__slide-container">
            <img
              src="~/assets/img/main_page_slide-img.png"
              alt="Картинка слайда"
              class="guarantee__slide-img guarantee__slide-img_1"
            />

            <p class="guarantee__slide-text">
              Компания <strong>ООО «Кубань Агро-продукт»</strong> существует более 10 лет, пройдя за
              это время путь от небольшого завода до производителя, пользующегося любовью
              покупателей по всей стране, от Калининграда до Владивостока. Основу нашей продукции
              составляют натуральные фрукты, вобравшие от плодородных кубанских земель все
              необходимые для здоровья человека витамины и минералы. Соки и напитки производятся на
              современном европейском оборудовании под строгим контролем качества в соответствии с
              СанПиН.
            </p>
          </div>

          <div class="guarantee__slide-img-bg"></div>
        </slide>

        <slide>
          <div class="guarantee__slide-container guarantee__slide-container_space-between">
            <p class="guarantee__slide-text guarantee__slide-text_pl">
              <span>ООО «Кубань Агро-продукт»</span> использует не только сырье лучшего качества, но
              и итальянские технологии производства, упаковки и хранения продукции. Современное
              оборудование позволяет сохранить максимум витаминов и полезных веществ. Для готовых
              напитков компания имеет собственные склады, где контролируются показатели влажности и
              температурный режим, — все для максимального сохранения натуральной силы фруктов и
              овощей! Качественная натуральная продукция – залог здоровья каждого члена вашей семьи!
            </p>

            <img
              src="~/assets/img/main_page_slide-img.png"
              alt="Картинка слайда"
              class="guarantee__slide-img guarantee__slide-img_2"
            />
          </div>

          <div class="guarantee__slide-img-bg_1"></div>
        </slide>

        <hooper-pagination slot="hooper-addons"></hooper-pagination>
      </hooper>
    </section>

    <section class="successful">
      <div class="successful__bg_peach"></div>
      <div class="successful__bg"></div>

      <h2 class="successful__title">Наш залог успеха</h2>

      <ul class="successful__list">
        <li class="successful-list__item">
          <div class="successful-list__icon icon__locally"></div>

          <div class="successful-list__info">
            <h4 class="successful-list__title">Лучшая география</h4>

            <p class="successful-list__text">
              При изготовлении соков и напитков мы используем вкусные сочные фрукты, которыми так
              знаменит Краснодарский край.
            </p>
          </div>
        </li>

        <li class="successful-list__item">
          <div class="successful-list__icon icon__belt"></div>

          <div class="successful-list__info">
            <h4 class="successful-list__title">Лучшее оборудование</h4>

            <p class="successful-list__text">
              Продукция производится на итальянском оборудовании с соблюдением всех технологических
              стандартов.
            </p>
          </div>
        </li>

        <li class="successful-list__item">
          <div class="successful-list__icon icon__checkmark"></div>

          <div class="successful-list__info">
            <h4 class="successful-list__title">Известный бренд</h4>

            <p class="successful-list__text">
              Нашу продукцию знают и любят покупатели по всей России благодаря ее высокому качеству
              и насыщенному, натуральному вкусу.
            </p>
          </div>
        </li>
      </ul>
    </section>

    <section id="products" class="products">
      <h2 class="products__title">Продукция</h2>

      <ul class="products__list">
        <li
          v-for="product in products"
          :key="product.id"
          class="products-list__item"
          @click="goTo(product)"
        >
          <img
            :src="require(`../assets/img/${product.img.toLowerCase()}.png`)"
            alt="Вид продукции"
            class="products__item-img"
          />

          <p class="products__item-text">{{ product.text }}</p>
        </li>
      </ul>

      <div class="products__raspberries-bg"></div>
      <div class="products__leaflet-bg"></div>
    </section>

    <section class="partners">
      <h2 class="partners__title">Наши партнеры</h2>

      <ul class="partners__list">
        <li v-for="partner in partners" :key="partner.id" class="partners-list__item">
          <img
            :src="require(`../assets/img/${partner.icon.toLowerCase()}.svg`)"
            :alt="partner.name"
          />
        </li>
      </ul>
    </section>
  </main>
</template>

<script>
import { Hooper, Slide, Pagination as HooperPagination } from 'hooper';
import 'hooper/dist/hooper.css';
const products = [
  {
    id: 1,
    idForFilter: 'bottleSmall',
    img: 'juices_walk_on_garden',
    text: 'Напитки «Прогулка по саду» 0,5л',
    value: '0,5',
    type: 'juice',
    name: 'Напитки',
  },
  {
    id: 2,
    idForFilter: 'bottleSmall_1',
    img: 'juices_walk_on_garden_1',
    text: 'Напитки «Прогулка по саду» 1л',
    value: '1',
    type: 'juice',
    name: 'Напитки',
  },
  {
    id: 3,
    idForFilter: 'bottleMiddle',
    img: 'uzvar_walk_on_garden',
    text: 'Узвары «Прогулка по саду» 3л',
    value: '3',
    type: 'uzvar',
    name: 'Узвары',
  },
  {
    id: 4,
    idForFilter: 'bottleMiddle',
    img: 'juices_walk_on_garden_3l',
    text: 'Напитки «Прогулка по саду» 3л',
    value: '3',
    type: 'juice',
    name: 'Напитки',
  },
  {
    id: 5,
    idForFilter: 'bottleBig',
    img: 'juices_walk_on_garden_5l',
    text: 'Напитки «Прогулка по саду» 5л',
    value: '5',
    type: 'juice',
    name: 'Напитки',
  },
  {
    id: 6,
    idForFilter: 'bottleBig',
    img: 'uzvar_walk_on_garden_5l',
    text: 'Узвары «Прогулка по саду» 5л',
    value: '5',
    type: 'uzvar',
    name: 'Узвары',
  },
  {
    id: 7,
    idForFilter: 'bottleMiddle',
    img: 'syrup_walk_on_garden',
    text: 'Сиропы «Прогулка по саду» 3л',
    value: '3',
    type: 'syrup',
    name: 'Сиропы',
  },
];
const partners = [
  {
    id: 1,
    icon: 'partner_globus',
    name: 'Глобус',
  },
  {
    id: 2,
    icon: 'partner_bread',
    name: 'Челны Хлеб',
  },
  {
    id: 3,
    icon: 'partner_luck',
    name: 'Универсам Удача',
  },
  {
    id: 4,
    icon: 'partner_shamsa',
    name: 'ГК Шамса',
  },
  {
    id: 5,
    icon: 'partner_ambar',
    name: 'Амбар',
  },
];
export default {
  name: 'Home',

  components: {
    Hooper,
    Slide,
    HooperPagination,
  },

  data() {
    return {
      products: [...products],
      partners: [...partners],
    };
  },

  head: {
    title: 'Главная',
  },

  methods: {
    goTo(product) {
      localStorage.setItem('product', JSON.stringify(product));
      this.$router.push('/Product');
    },
  },
};
</script>

<style lang="scss" scoped>
.header {
  position: relative;
  text-align: left;
  padding: 258px 100px 0;
  height: 948px;
}
.header__title {
  font-family: Montserrat Alternates;
  font-style: normal;
  font-weight: bold;
  font-size: 64px;
  line-height: 119.41%;
  color: #4b4961;
  margin-bottom: 20px;
}
.header__description {
  font-family: Comfortaa;
  font-style: normal;
  font-weight: normal;
  font-size: 28px;
  line-height: 31px;
  color: #95979b;
  max-width: 915px;
}
.header__button {
  display: inline-block;
  font-family: 'comfortaa';
  text-decoration: none;
  color: #000;
  background: linear-gradient(269.21deg, #ffd25a 0.49%, #ffc52b 100%);
  border-radius: 10px;
  font-size: 20px;
  transition-duration: 0.5s;

  padding: 20px 43px;
  margin-top: 43px;

  &:hover {
    box-shadow: 0px 0px 15px rgba(255, 210, 90, 0.6);
    background: linear-gradient(269.21deg, #ffd25a 0.49%, #ffc52b 100%);
  }

  &:active {
    box-shadow: 0px 0px 15px rgba(255, 210, 90, 0.4), inset 0px 4px 4px rgba(0, 0, 0, 0.1);
    transition-duration: 0s;
    background: linear-gradient(269.21deg, #ffd25a 0.49%, #ffc52b 100%);
  }
}

.header__bg {
  position: absolute;
  top: -144px;
  left: 0;
  right: 0;
  bottom: 0;

  background-image: url('~/assets/img/main_page_header_bg.svg');
  background-size: cover;
  background-position: center;
  background-repeat: repeat-x;

  z-index: -1;
}
.header__leaflet_1 {
  position: absolute;
  top: 100px;
  left: -67px;

  width: 241px;
  height: 111px;

  background-image: url('~/assets/img/main_page_leaflet_1.svg');
  background-size: auto;
  background-position: center;
  background-repeat: no-repeat;
}
.header__leaflet_2 {
  position: absolute;
  top: 0;
  right: 0;

  width: 241px;
  height: 201px;

  background-image: url('~/assets/img/leaflet_1.svg');
  background-size: auto;
  background-position: center;
  background-repeat: no-repeat;
}
.header__leaflet_3 {
  position: absolute;
  bottom: 70px;
  left: -16px;

  width: 331px;
  height: 133px;

  background-image: url('~/assets/img/leaflet_2.svg');
  background-size: auto;
  background-position: center;
  background-repeat: no-repeat;
}
.header__leaflet_4 {
  position: absolute;
  bottom: 275px;
  right: 0;

  width: 155px;
  height: 119px;

  background-image: url('~/assets/img/main_page_leaflet_2.svg');
  background-size: auto;
  background-position: center;
  background-repeat: no-repeat;
}
.header__leaflet_5 {
  position: absolute;
  top: 147px;
  right: 643px;

  width: 155px;
  height: 168px;

  background-image: url('~/assets/img/main_page_leaflet_3.svg');
  background-size: auto;
  background-position: center;
  background-repeat: no-repeat;
  z-index: -1;
}
.header__bg-juice {
  position: absolute;
  bottom: 0;
  right: 225px;

  width: 580px;
  height: 1083px;

  background-image: url('~/assets/img/main_page_juice_view.png');
  background-size: auto;
  background-position: center;
  background-repeat: no-repeat;
  z-index: -1;
}

.guarantee {
  position: relative;
  margin: 230px 0 400px;
  height: 923px;
}
.guarantee__some-bg {
  position: absolute;
  top: -933px;
  right: 0;

  width: 334px;
  height: 984px;

  background-image: url('~/assets/img/main_page_some_bg.png');
  background-size: auto;
  background-position: center;
  background-repeat: no-repeat;

  z-index: -2;
}
.guarantee__title {
  font-family: Montserrat Alternates;
  font-style: normal;
  font-weight: bold;
  font-size: 72px;
  line-height: 88px;
  color: #484848;

  padding-left: 100px;
}
.guarantee__slide-container {
  display: flex;
  align-items: center;
  justify-content: space-between;
  height: 889px;
}
.guarantee__slide-container_space-between {
  justify-content: space-between;
  gap: 0;
}
.guarantee__slide-img {
  width: 727px;
  height: 667px;

  filter: drop-shadow(18px 21px 51px rgba(255, 204, 68, 0.2));
}
.guarantee__slide-img_1 {
  border-radius: 0 10px 10px 0;
}
.guarantee__slide-img_2 {
  border-radius: 10px 0 0 10px;
  margin-right: -63px;
}
.guarantee__slide-img-bg {
  position: absolute;
  bottom: 0;
  left: -32px;

  width: 889px;
  height: 889px;

  background-image: url('~/assets/img/slide_img_bg.png');
  background-size: auto;
  background-position: center;
  background-repeat: no-repeat;

  z-index: -1;
}
.guarantee__slide-img-bg_1 {
  position: absolute;
  bottom: 0;
  right: -110px;

  width: 889px;
  height: 889px;

  background-image: url('~/assets/img/slide_img_bg_1.png');
  background-size: auto;
  background-position: center;
  background-repeat: no-repeat;

  z-index: -1;
}
.guarantee__slide-text {
  font-family: Raleway;
  font-style: normal;
  font-weight: normal;
  font-size: 36px;
  line-height: 150%;
  color: #6a6a6a;

  max-width: 1037px;

  span {
    font-weight: 500;
  }
}
.guarantee__slide-text_pl {
  padding-left: 70px;
}

.successful {
  position: relative;
  height: 300px;

  padding: 0 100px;
  margin-bottom: 300px;
}
.successful__bg {
  position: absolute;
  top: -550px;
  right: 0;

  width: 100%;
  height: 1100px;

  background-image: url('~/assets/img/successful_bg.png');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;

  z-index: -1;
}
.successful__bg_peach {
  position: absolute;
  top: -430px;
  right: 0;

  width: 574px;
  height: 758px;

  background-image: url('~/assets/img/peach_bg.png');
  background-size: auto;
  background-position: center;
  background-repeat: no-repeat;
}
.successful__title {
  font-family: Montserrat Alternates;
  font-style: normal;
  font-weight: bold;
  font-size: 72px;
  line-height: 88px;
  color: #484848;

  margin-bottom: 127px;
}
.successful__list {
  display: flex;
  align-items: flex-start;
  justify-content: space-between;
}
.successful-list__item {
  display: flex;
  align-items: flex-start;
  gap: 25px;
}
.successful-list__info {
  max-width: 427px;
}
.successful-list__title {
  font-family: Rubik;
  font-style: normal;
  font-weight: bold;
  font-size: 28px;
  line-height: 33px;
  color: #484848;

  margin-bottom: 16px;
}
.successful-list__text {
  font-family: Rubik;
  font-style: normal;
  font-weight: normal;
  font-size: 20px;
  line-height: 24px;
  color: #484848;
}
.successful-list__icon {
  width: 102px;
  height: 102px;

  background-size: auto;
  background-position: center;
  background-repeat: no-repeat;
}
.icon__locally {
  background-image: url('~/assets/img/successful_locally.svg');
}
.icon__belt {
  background-image: url('~/assets/img/successful_belt.svg');
}
.icon__checkmark {
  background-image: url('~/assets/img/successful_checkmark.svg');
}

.products {
  position: relative;
  padding: 0 100px;
  margin-bottom: 167px;
}
.products__title {
  font-family: Montserrat Alternates;
  font-style: normal;
  font-weight: bold;
  font-size: 72px;
  line-height: 88px;
  color: #484848;

  margin-bottom: 130px;
}
.products__list {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  column-gap: 30px;
  row-gap: 90px;
}
.products-list__item {
  box-sizing: border-box;
  cursor: pointer;
  transition: transform 0.4s;
  border-bottom: 6px solid transparent;
  border-radius: 0 0 10px 10px;
  &:hover {
    border-bottom: 6px solid #ffd25a;
    border-radius: 0 0 10px 10px;

    transform: translateY(-10px);
    transition: transform 0.2s;
  }
}
.products__item-img {
  width: 403px;
  border-radius: 10px 10px 0 0;
}
.products__item-text {
  font-family: Raleway;
  font-style: normal;
  font-weight: 600;
  font-size: 20px;
  line-height: 23px;
  color: #525252;

  background: #faf9f8;
  border-radius: 0 0 10px 10px;
  padding: 19px 18px 36px;
}
.products__raspberries-bg {
  position: absolute;
  bottom: -175px;
  left: -98px;

  width: 405px;
  height: 405px;

  background-image: url('~/assets/img/raspberries_bg.png');
  background-size: auto;
  background-position: center;
  background-repeat: no-repeat;
}
.products__leaflet-bg {
  position: absolute;
  bottom: -180px;
  right: 0;

  width: 232px;
  height: 144px;

  background-image: url('~/assets/img/products_leaflet.png');
  background-size: auto;
  background-position: center;
  background-repeat: no-repeat;
}

.partners {
  padding: 0 100px;
  margin-bottom: 150px;
}
.partners__list {
  display: flex;
  column-gap: 150px;
  align-items: center;
  justify-content: center;
  flex-wrap: wrap;
}
.partners__title {
  font-family: Montserrat Alternates;
  font-style: normal;
  font-weight: bold;
  font-size: 72px;
  line-height: 88px;
  color: #484848;

  margin-bottom: 130px;
}

@media (min-width: 2000px) {
  .guarantee__slide-img-bg {
    left: 200px;
  }
  .guarantee__slide-img-bg_1 {
    right: 230px;
  }
  .guarantee__slide-img_2 {
    margin-right: 0;
  }
}
</style>

<style lang="scss">
.guarantee .hooper {
  margin-top: 20px;
}
.hooper-slide {
  position: relative;
}
.hooper-indicators {
  li:not(:last-child) {
    margin-right: 35px;
  }
}
.hooper-indicator {
  width: 24px;
  height: 24px;

  border: 1px solid #ffd25a;
  border-radius: 20px;

  margin: 0;

  &.is-active {
    width: 30px;
    height: 30px;
    background: linear-gradient(269.21deg, #ffd25a 0.49%, #ffc52b 100%);
  }

  &:hover {
    background-color: #ffd25a;
  }
}

@media (min-width: 2000px) {
  .hooper-slide {
    padding: 0 200px;
  }
}
</style>
