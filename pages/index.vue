<template>
  <main class="container">
    <section class="header">
      <div class="header__bg"></div>
      <div class="header__leaflet_1"></div>
      <div class="header__leaflet_2"></div>
      <div class="header__leaflet_3"></div>
      <div class="header__leaflet_4"></div>
      <div class="header__leaflet_5"></div>
      <div class="header__some_bg"></div>
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
  </main>
</template>

<script>
export default {
  name: 'Home',
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
.header__some_bg {
  position: absolute;
  bottom: 0;
  right: 0;

  width: 334px;
  height: 345px;

  background-image: url('~/assets/img/main_page_some_bg.png');
  background-size: auto;
  background-position: center;
  background-repeat: no-repeat;

  z-index: -2;
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
</style>
