<template>
  <main class="main">
    <section class="contacts">
      <h1 class="contacts__title">Контакты</h1>

      <a class="contacts__phone" href="tel:88616265015">8 (86162) 6-50-15</a>

      <div class="contacts__info">
        <p class="contacts__text">
          Интересующие вас вопросы, касающиеся производства, выпуска, ассортимента и покупки нашей
          продукции вы можете задать, позвонив по телефону горячей линии
        </p>

        <p class="contacts__text">
          Мы внимательно и трепетно относимся к производству продукции, поэтому будем рады получить
          обратную связь и выслушать ваши предложения
        </p>
      </div>

      <div class="contacts__bg"></div>
      <div class="contacts__leaflet_bg1"></div>
      <div class="contacts__leaflet_bg2"></div>
      <div class="contacts__leaflet_bg3"></div>
    </section>

    <section class="address">
      <div class="address__juice-bg"></div>

      <div class="address__container">
        <div class="address__info">
          <h2 class="address__title">Юридический и почтовый адрес</h2>

          <p class="address__text">353460, Краснодарский край, г. Геленджик, ул. Курзальная, 19</p>

          <p class="address__text">353460, Краснодарский край, Динской район, ст. Динская А/Я 10</p>

          <p class="address__text address__email">
            email: <a class="email" href="mailto:ooo_kap@mail.ru">ooo_kap@mail.ru</a>
          </p>

          <a class="address__phone" href="tel:89182893779">8 (918) 289-37-79</a>
        </div>

        <div class="address__production">
          <h2 class="address__title">Производство и склад</h2>

          <p class="address__text address__text_middle">
            353200, Краснодарский край, Динской р-н, ст. Динская, ул. Краснодарская, 15 а.
          </p>

          <p class="address__text address__email">
            email: <a class="email" href="mailto:kap_sklad@mail.ru">kap_sklad@mail.ru</a>
          </p>

          <a class="address__phone" href="tel:89182893779">8 (918) 289-37-79</a>
        </div>
      </div>

      <hr />

      <h2 class="address__title">ООО “Кубань Агро-продукт”</h2>

      <div class="company">
        <div class="company__info">
          <p class="company-info__text">
            <span class="company-info__title">ИНН</span>
            2304058736
          </p>

          <p class="company-info__text">
            <span class="company-info__title">ОГРН</span>
            1102304002096 ОКАТО 03408000000
          </p>

          <p class="company-info__text">
            <span class="company-info__title">ОКВЭД</span>
            11/07/2 ОКПО 68485693 ОКТМО 03708000
          </p>

          <p class="company-info__text">
            <span class="company-info__title">ОКОГУ</span>
            4210014 ОКФС 16 ОКОПФ 12300
          </p>
        </div>

        <div class="company__info">
          <p class="company-info__text">
            <span class="company-info__title">р/сч</span>
            40702810826020006795 "РОСТОВСКИЙ" филиал АО "АЛЬФА-БАНК" г. Ростов-на-Дону
          </p>

          <p class="company-info__text">
            <span class="company-info__title">к/сч</span>
            30101810500000000207
          </p>

          <p class="company-info__text">
            <span class="company-info__title">БИК</span>
            046015207
          </p>
        </div>
      </div>
    </section>

    <div class="ymap" style="position: relative; overflow: hidden">
      <script
        type="text/javascript"
        charset="utf-8"
        async
        src="https://api-maps.yandex.ru/services/constructor/1.0/js/?um=constructor%3A0a220d3ce1e2e203a62c8182b6266a0a13804b8e5cde4aa79df0951578a59951&amp;width=100%25&amp;height=491&amp;lang=ru_RU&amp;scroll=false"
      ></script>
    </div>
  </main>
</template>

<script>
export default {
  name: 'Contacts',

  head: {
    title: 'Контакты',
  },
};
</script>

<style scoped lang="scss">
.contacts {
  position: relative;
  padding: 100px 100px;
}
.contacts__bg {
  position: absolute;
  top: -270px;
  left: 0;
  right: 0;
  bottom: 0;

  background-image: url('~/assets/img/wave_bg.svg');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;

  z-index: -1;
}
.contacts__leaflet_bg1 {
  position: absolute;
  top: 70px;
  right: 390px;

  width: 274px;
  height: 119px;

  background-image: url('~/assets/img/company_leaflet_bg.png');
  background-size: auto;
  background-position: center;
  background-repeat: no-repeat;
}
.contacts__leaflet_bg2 {
  position: absolute;
  top: 152px;
  right: -90px;

  width: 236px;
  height: 114px;

  background-image: url('~/assets/img/leaflet_2.svg');
  background-size: auto;
  background-position: center;
  background-repeat: no-repeat;
}
.contacts__leaflet_bg3 {
  position: absolute;
  top: 60px;
  right: 0;

  width: 288px;
  height: 145px;

  background-image: url('~/assets/img/company_leaflet_2.png');
  background-size: auto;
  background-position: center;
  background-repeat: no-repeat;
}
.contacts__title {
  font-family: Montserrat Alternates;
  font-style: normal;
  font-weight: bold;
  font-size: 72px;
  line-height: 88px;
  color: #4b4961;

  margin-bottom: 60px;
}
.contacts__phone {
  font-family: Montserrat Alternates;
  font-style: normal;
  font-weight: bold;
  font-size: 36px;
  line-height: 44px;
  color: #4b4961;
}
.contacts__info {
  display: flex;
  align-items: center;
  gap: 30px;

  margin-top: 10px;
}
.contacts__text {
  font-family: Rubik;
  font-style: normal;
  font-weight: normal;
  font-size: 24px;
  line-height: 28px;
  color: #95979b;
}

.address {
  position: relative;
  padding: 0 100px;
}
.address__juice-bg {
  position: absolute;
  top: 135px;
  right: 0;

  width: 263px;
  height: 350px;

  background-image: url('~/assets/img/company_juice_bg.png');
  background-size: auto;
  background-position: center;
  background-repeat: no-repeat;
}
.address__title {
  font-family: Montserrat Alternates;
  font-style: normal;
  font-weight: bold;
  font-size: 42px;
  line-height: 51px;
  color: #4b4961;

  margin-bottom: 40px;
}
.address__container {
  display: flex;
  align-items: baseline;
  gap: 135px;
}
.address__info {
  flex: 1 0 0;
}
.address__production {
  flex: 1 0 0;
}
.address__email {
  margin: 12px 0 14px;
}
.email {
  text-decoration-line: underline;
  color: #95979b;
  font-weight: normal;
}
.address__text {
  font-family: Rubik;
  font-style: normal;
  font-weight: normal;
  font-size: 24px;
  line-height: 28px;
  color: #95979b;
}
.address__text_middle {
  width: 545px;
}
.address__phone {
  font-family: Montserrat Alternates;
  font-style: normal;
  font-weight: bold;
  font-size: 24px;
  line-height: 29px;
  color: #4b4961;
}

.company {
  display: flex;
  align-items: center;
  gap: 150px;

  margin-bottom: 55px;
}
.company__info {
  flex: 1 0 0;
}
.company-info__text {
  font-family: Rubik;
  font-style: normal;
  font-weight: normal;
  font-size: 24px;
  line-height: 200%;
  color: #5b5b5b;
}
.company-info__title {
  font-family: Rubik;
  font-style: normal;
  font-weight: 500;
  font-size: 24px;
  line-height: 200%;
  color: #5b5b5b;
}

hr {
  width: 90%;
  height: 2px;
  background: #efefef;

  margin: 90px 0;
}
</style>
