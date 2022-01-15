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

      <button class="header__button">Смотреть продукцию</button>
    </section>

    <section class="guarantee">
      <div class="guarantee__some-bg"></div>

      <h2 class="guarantee__title">Годы опыта — гарантии качества</h2>

      <hooper
        style="height: 889px"
        :wheel-control="false"
        :auto-play="true"
        :play-speed="10000"
        :transition="3000"
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
  </main>
</template>

<script>
import { Hooper, Slide, Pagination as HooperPagination } from 'hooper';
import 'hooper/dist/hooper.css';
export default {
  name: 'Home',

  components: {
    Hooper,
    Slide,
    HooperPagination,
  },

  head: {
    title: 'Главная',
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
  font-family: 'comfortaa';
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
}

.guarantee {
  position: relative;
  margin: 230px 0 200px;
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
  gap: 96px;
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
}
</style>
