<template>
  <main class="container">
    <section class="header">
      <div class="header__bg"></div>
      <div class="header__leaflet_1"></div>
      <div class="header__leaflet_2"></div>
      <div class="header__leaflet_3"></div>
      <div class="header__leaflet_4"></div>
      <div class="header__bg-juice"></div>

      <h1 class="title_main header__title">
        Все витамины Кубани <br />
        в каждой упаковке!
      </h1>

      <img
        class="header__juice-img"
        src="~/assets/img/main_page_juice_view.png"
        alt="Сок апельсиновый в бутылке объёмом пол литра"
      />

      <p class="header__description">
        Наша компания производит и реализует оптом и в розницу соки, натуральные напитки из
        сухофруктов, безалкогольную и газированную продукцию.
      </p>

      <a class="header__button" href="#products">Смотреть продукцию</a>
    </section>

    <section class="guarantee">
      <div class="guarantee__some-bg"></div>

      <h2 class="title_main guarantee__title">Годы опыта — гарантии качества</h2>

      <swiper :options="swiperOption">
        <swiper-slide>
          <div class="guarantee__slide-container">
            <img
              src="~/assets/img/main_page_slide-img.png"
              alt="Картинка слайда"
              class="guarantee__slide-img"
            />

            <img
              src="~/assets/img/main_page_slide-img_mobile.png"
              alt="Картинка слайда"
              class="guarantee__slide-img_mobile"
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
        </swiper-slide>

        <swiper-slide>
          <div class="guarantee__slide-container">
            <img
              src="~/assets/img/main_page_slide-img_mobile.png"
              alt="Картинка слайда"
              class="guarantee__slide-img_mobile"
            />

            <p class="guarantee__slide-text">
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
        </swiper-slide>

        <div slot="pagination" class="swiper-pagination"></div>
      </swiper>
    </section>

    <section class="successful">
      <div class="successful__bg_peach"></div>
      <div class="successful__bg"></div>
      <div class="successful__bg_mobile"></div>

      <h2 class="title_main successful__title">Наш залог успеха</h2>

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
      <h2 class="title_main products__title">Продукция</h2>

      <ul class="products__list">
        <li
          v-for="product in products"
          :key="product.id"
          class="products-list__item"
          @click="saveProductToLocalStorage(product)"
        >
          <nuxt-link class="link" to="/product" exact-active-class="link-active">
            <img
              :src="require(`../assets/img/${product.img.toLowerCase()}.png`)"
              alt="Вид продукции"
              class="products__item-img"
            />

            <p class="products__item-text">{{ product.text }}</p>
          </nuxt-link>
        </li>
      </ul>

      <div class="products__raspberries-bg"></div>
      <div class="products__leaflet-bg"></div>
    </section>

    <section class="partners">
      <h2 class="title_main partners__title">Наши партнеры</h2>

      <ul class="partners__list">
        <li v-for="partner in partners" :key="partner.id" class="partners-list__item">
          <img
            :src="require(`../assets/img/${partner.icon.toLowerCase()}.png`)"
            :alt="partner.name"
            class="partners-list__item-image"
          />
        </li>
      </ul>
    </section>
  </main>
</template>

<script>
import { Swiper, SwiperSlide } from 'vue-awesome-swiper';
import 'swiper/css/swiper.css';
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
  {
    id: 6,
    icon: 'partner_nahodka',
    name: 'Находка',
  },
  {
    id: 7,
    icon: 'partner_pobeda',
    name: 'Победа',
  },
];
export default {
  name: 'Home',

  components: {
    Swiper,
    SwiperSlide,
  },

  data() {
    return {
      products: [...products],
      partners: [...partners],

      swiperOption: {
        grabCursor: true,
        speed: 1000,
        autoplay: {
          delay: 5500,
          disableOnInteraction: false,
          pauseOnMouseEnter: true,
        },
        pagination: {
          el: '.swiper-pagination',
          dynamicBullets: true,
          clickable: true,
        },
      },
    };
  },

  head: {
    title: 'Главная',
  },

  methods: {
    saveProductToLocalStorage(product) {
      localStorage.setItem('product', JSON.stringify(product));
    },
  },
};
</script>

<style lang="scss" scoped>
.title_main {
  font-family: Montserrat Alternates;
  font-style: normal;
  font-weight: bold;
  font-size: 64px;
  line-height: 120%;
  color: #484848;
}

.header {
  position: relative;
  text-align: left;
  padding: 140px 100px 0;
  height: 830px;
}
.header__title {
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
  top: -260px;
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
  top: 0;
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
.header__bg-juice {
  position: absolute;
  bottom: 25px;
  right: 235px;

  width: 630px;
  height: 925px;

  background-image: url('~/assets/img/main_page_juice_view.png');
  background-size: contain;
  background-position: center;
  background-repeat: no-repeat;
  z-index: -1;
}
.header__juice-img {
  display: none;
}

.guarantee {
  position: relative;
  margin: 230px 0 400px;
  height: 700px;
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
  padding-left: 100px;
}
.guarantee__slide-container {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 730px;
}
.guarantee__slide-img {
  width: 600px;
  filter: drop-shadow(18px 21px 51px rgba(255, 204, 68, 0.2));
}
.guarantee__slide-img_mobile {
  display: none;
}
.guarantee__slide-img_2 {
  transform: scale(-1, 1);
}
.guarantee__slide-img-bg {
  position: absolute;
  bottom: 0;
  left: -20px;

  width: 800px;
  height: 800px;

  background-image: url('~/assets/img/slide_img_bg.png');
  background-size: contain;
  background-position: center;
  background-repeat: no-repeat;

  z-index: -1;
}
.guarantee__slide-img-bg_1 {
  position: absolute;
  bottom: 45px;
  right: -30px;

  width: 678px;
  height: 668px;

  background-image: url('~/assets/img/slide_img_bg_1.png');
  background-size: contain;
  background-position: center;
  background-repeat: no-repeat;

  z-index: -1;
}
.guarantee__slide-text {
  font-family: Raleway;
  font-style: normal;
  font-weight: normal;
  font-size: 28px;
  line-height: 150%;
  color: #6a6a6a;

  max-width: 1037px;

  span {
    font-weight: 500;
  }
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
.successful__bg_mobile {
  display: none;
}
.successful__bg_peach {
  position: absolute;
  top: -430px;
  right: 0;

  width: 574px;
  height: 758px;

  background-image: url('~/assets/img/peach_bg.png');
  background-size: contain;
  background-position: center;
  background-repeat: no-repeat;
}
.successful__title {
  margin-bottom: 127px;
}
.successful__list {
  display: flex;
  align-items: flex-start;
  justify-content: space-between;
  flex-wrap: wrap;
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

  background-size: contain;
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
  margin-bottom: 60px;
}
.products__list {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  column-gap: 30px;
  row-gap: 70px;
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
  padding: 0 100px 150px;
  border-bottom: 1px solid #eaeaea;
}
.partners__list {
  display: flex;
  column-gap: 70px;
  row-gap: 35px;
  align-items: center;
  justify-content: center;
  flex-wrap: wrap;
}
.partners-list__item-image {
  width: 180px;
}
.partners__title {
  margin-bottom: 130px;
}

@media (min-width: 2000px) {
  .guarantee {
    height: 800px;
  }
  .guarantee__some-bg {
    top: -780px;
  }
  .guarantee__slide-container {
    gap: 300px;
    height: 900px;
  }
  .guarantee__slide-img {
    width: 700px;
  }
  .guarantee__slide-img-bg {
    left: 200px;
    bottom: 80px;
  }
  .guarantee__slide-img-bg_1 {
    right: 230px;
    bottom: 115px;
  }
  .guarantee__slide-img_2 {
    margin-right: 0;
  }

  .partners__list {
    justify-content: space-between;
  }
}
@media (max-width: 1900px) {
  .title_main {
    font-size: 47px;
  }
  .header__description {
    font-size: 26px;
    max-width: 790px;
  }
  .header__bg-juice {
    right: 30px;
  }

  .guarantee {
    height: 600px;
  }
  .guarantee__slide-container {
    margin: 0 auto;
    max-width: 90%;
  }
  .guarantee__slide-text {
    font-size: 26px;
  }
  .guarantee__slide-img {
    width: 550px;
  }
  .guarantee__slide-img-bg {
    width: 700px;
    height: 700px;
    bottom: 20px;
  }

  .successful__bg_peach {
    width: 440px;
    height: 585px;
    top: -308px;
  }
  .successful__list {
    gap: 30px;
  }
  .successful-list__info {
    max-width: 350px;
  }
  .successful-list__item {
    gap: 10px;
  }
  .successful-list__icon {
    width: 73px;
    height: 73px;
  }
}
@media (max-width: 1440px) {
  .title_main {
    font-size: 42px;
  }

  .header {
    padding: 90px 60px 0;
    height: 620px;
  }
  .header__bg-juice {
    display: none;
  }
  .header__leaflet_1 {
    top: -30px;
  }
  .header__leaflet_3 {
    bottom: 25px;
    left: -103px;
  }
  .header__leaflet_4 {
    bottom: 120px;
  }
  .header__juice-img {
    display: block;
    width: 420px;
    float: right;
    margin-top: -220px;
  }
  .header__title {
    font-size: 36px;
  }
  .header__description {
    font-size: 24px;
  }
  .header__leaflet_2 {
    width: 150px;
    height: 120px;
    background-size: contain;
  }

  .guarantee {
    margin: 110px 0 180px;
  }
  .guarantee__some-bg {
    top: -725px;
    width: 253px;
    height: 845px;
    background-size: contain;
  }
  .guarantee__title {
    padding-left: 60px;
  }
  .guarantee__slide-container {
    height: 580px;
  }
  .guarantee__slide-text {
    font-size: 22px;
  }
  .guarantee__slide-img {
    width: 490px;
  }
  .guarantee__slide-img-bg {
    width: 550px;
    height: 550px;
    bottom: 10px;
  }
  .guarantee__slide-img-bg_1 {
    width: 550px;
    height: 550px;
    bottom: 20px;
  }

  .successful {
    padding: 0 60px;
  }
  .successful__bg_peach {
    width: 360px;
    height: 495px;
    top: -225px;
  }
  .successful-list__title {
    font-size: 24px;
    margin-bottom: 5px;
  }
  .successful-list__text {
    font-size: 16px;
  }

  .products {
    padding: 0 60px;
  }
  .partners {
    padding: 0 60px 150px;
  }
}
@media (max-width: 1024px) {
  .title_main {
    font-size: 36px;
  }

  .header {
    height: 440px;
    padding: 40px 25px 0;
  }
  .header__title {
    font-size: 30px;
  }
  .header__description {
    font-size: 16px;
  }
  .header__juice-img {
    width: 300px;
    margin-top: -150px;
  }
  .header__button {
    font-size: 16px;
    padding: 16px;
    margin-top: 60px;
  }
  .header__leaflet_1 {
    display: none;
  }
  .header__leaflet_2 {
    width: 115px;
    height: 95px;
  }
  .header__leaflet_3 {
    display: none;
  }
  .header__leaflet_4 {
    width: 100px;
    height: 180px;
    background-size: contain;
    bottom: 65px;
  }

  .guarantee {
    margin: 30px 0 0;
  }
  .guarantee__some-bg {
    top: -315px;
    width: 117px;
    height: 387px;
  }
  .guarantee__title {
    padding-left: 25px;
  }
  .guarantee__slide-container {
    height: 470px;
  }
  .guarantee__slide-img {
    width: 340px;
  }
  .guarantee__slide-img-bg {
    width: 430px;
    height: 430px;
    bottom: 20px;
  }
  .guarantee__slide-img-bg_1 {
    width: 440px;
    height: 440px;
    bottom: 24px;
  }
  .guarantee__slide-text {
    font-size: 15px;
  }

  .successful {
    padding: 0 25px;
  }
  .successful__bg_peach {
    width: 295px;
    height: 390px;
    top: -150px;
  }
  .successful__list {
    justify-content: center;
  }
  .successful-list__item {
    gap: 30px;
  }

  .products {
    padding: 0 25px;
  }
  .products__item-img {
    width: 330px;
  }
  .products__item-text {
    font-size: 16px;
    padding: 18px 20px;
  }

  .partners {
    padding: 0 25px 70px;
  }
  .partners__title {
    margin-bottom: 50px;
  }
  .partners-list__item-image {
    width: 120px;
  }
}
@media (max-width: 768px) {
  .successful__title {
    margin-bottom: 34px;
  }
}
@media (max-width: 767px) {
  .title_main {
    font-size: 30px;
  }

  .header {
    height: 750px;
  }
  .header__title {
    font-size: 24px;
    margin-bottom: 10px;
  }
  .header__description {
    line-height: 18px;
  }
  .header__button {
    margin-top: 20px;
  }
  .header__juice-img {
    float: none;
    width: 293px;
    margin-top: -65px;
  }
  .header__leaflet_3 {
    display: block;
    width: 235px;
    height: 120px;
    bottom: 290px;
    transform: rotate(-42deg);
    background-size: contain;
  }
  .header__leaflet_4 {
    bottom: 240px;
  }
  .header__leaflet_2 {
    top: 120px;
  }

  .guarantee {
    height: 600px;
    margin: 30px 0 150px;
  }
  .guarantee__some-bg {
    top: -270px;
    width: 85px;
    height: 288px;
    z-index: 1;
  }
  .guarantee__slide-container {
    flex-direction: column;
    justify-content: normal;
    margin: 0 25px;
    max-width: 100%;
  }
  .guarantee__slide-img {
    display: none;
  }
  .guarantee__slide-img_mobile {
    display: block;
  }
  .guarantee__slide-img-bg {
    display: none;
  }
  .guarantee__slide-img-bg_1 {
    display: none;
  }

  .successful__bg_peach {
    display: none;
  }
  .successful__bg {
    display: none;
  }
  .successful__bg_mobile {
    display: block;
    position: absolute;
    top: -68px;
    left: 0;

    width: 100%;
    height: 620px;

    background-image: url('~/assets/img/successful_bg_mobile.png');
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;

    z-index: -1;
  }
  .successful-list__icon {
    flex-shrink: 0;
    width: 58px;
    height: 58px;
  }
  .successful-list__title {
    font-size: 20px;
  }
  .successful-list__text {
    font-size: 14px;
  }
  .successful-list__item {
    gap: 10px;
  }

  .products {
    margin-bottom: 60px;
  }
  .products__title {
    margin-bottom: 20px;
  }
  .products__list {
    gap: 14px;
  }
  .products__raspberries-bg {
    display: none;
  }
  .products__leaflet-bg {
    display: none;
  }

  .swiper-container {
    height: 100%;
  }
}
@media (max-width: 425px) {
  .title_main {
    font-size: 24px;
  }

  .header {
    padding: 40px 15px 0;
  }
  .header__juice-img {
    margin: -65px auto 0;
  }
  .header__button {
    width: 100%;
    text-align: center;
  }
  .header__leaflet_2 {
    width: 90px;
  }
  .header__leaflet_4 {
    width: 75px;
  }

  .guarantee {
    height: 600px;
    margin: 0 0 150px;
  }
  .guarantee__title {
    padding-left: 15px;
  }
  .guarantee__slide-container {
    margin: 0 15px;
  }
  .guarantee__some-bg {
    top: -130px;
    width: 40px;
    height: 130px;
  }

  .successful {
    padding: 0 15px;
  }

  .products {
    padding: 0 15px;
  }
  .partners {
    padding: 0 15px 70px;
  }
  .partners__title {
    margin-bottom: 32px;
  }
  .partners-list__item-image {
    width: 110px;
  }
}
</style>

<style lang="scss">
.swiper-pagination-bullet {
  width: 24px;
  height: 24px;
  background: linear-gradient(269.21deg, #ffd25a 0.49%, #ffc52b 100%);
}

@media (max-width: 425px) {
  .swiper-pagination-bullet {
    width: 19px;
    height: 19px;
  }
}
</style>
