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

          <p class="address__text address__text_mb">
            353460, Краснодарский край, г. Геленджик, ул. Курзальная, 19
          </p>

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
        src="https://api-maps.yandex.ru/services/constructor/1.0/js/?um=constructor%3A0a220d3ce1e2e203a62c8182b6266a0a13804b8e5cde4aa79df0951578a59951&amp;width=100%25&amp;height=100%&amp;lang=ru_RU&amp;scroll=false"
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
main {
  overflow-x: hidden;
}
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
  font-size: 62px;
  line-height: 88px;
  color: #4b4961;

  margin-bottom: 60px;
}
.contacts__phone {
  font-family: Montserrat Alternates;
  font-style: normal;
  font-weight: bold;
  font-size: 30px;
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
  gap: 65px;
}
.address__info {
  flex: 1 0 50%;
}
.address__production {
  flex: 1 0 50%;
}
.address__email {
  margin: 12px 0 14px;
}
.email {
  border-bottom: 1px solid #95979b;
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

.ymap {
  height: 491px;
}

hr {
  width: 90%;
  height: 2px;
  background: #efefef;

  margin: 90px 0;
}
@media (min-width: 2000px) {
  .contacts__title {
    font-size: 72px;
  }
  .contacts__phone {
    font-size: 36px;
  }
  .contacts__text {
    font-size: 28px;
  }
}
@media (max-width: 1440px) {
  .contacts {
    padding: 100px 60px;
  }
  .contacts__title {
    font-size: 46px;
  }
  .contacts__phone {
    font-size: 30px;
  }
  .contacts__text {
    font-size: 20px;
  }
  .contacts__leaflet_bg1 {
    background-size: contain;
    right: 330px;
  }
  .contacts__leaflet_bg2 {
    background-size: contain;
    top: 130px;
  }
  .contacts__leaflet_bg3 {
    background-size: contain;
    width: 200px;
  }

  .address {
    padding: 0 60px;
  }
  .address__title {
    font-size: 30px;
    margin-bottom: 20px;
  }
  .address__text {
    font-size: 20px;
  }
  .address__phone {
    font-size: 20px;
  }
  .address__container {
    gap: 55px;
  }
  .address__juice-bg {
    background-size: contain;
    top: 100px;
    width: 182px;
    height: 424px;
  }

  .company-info__text {
    font-size: 20px;
  }
  .company-info__title {
    font-size: 20px;
  }

  hr {
    margin: 60px 0;
  }
}
@media (max-width: 1024px) {
  .contacts {
    padding: 60px 25px;
  }
  .contacts__leaflet_bg3 {
    width: 155px;
  }
  .contacts__leaflet_bg2 {
    top: 118px;
  }
  .contacts__leaflet_bg1 {
    display: none;
  }
  .contacts__title {
    font-size: 36px;
    margin-bottom: 0;
  }
  .contacts__phone {
    font-size: 24px;
  }
  .contacts__text {
    font-size: 16px;
    line-height: 22px;
  }

  .address {
    padding: 0 25px;
  }
  .address__container {
    gap: 40px;
  }
  .address__title {
    font-size: 24px;
    line-height: 36px;
  }
  .address__text {
    font-size: 16px;
    width: 90%;
  }
  .address__email {
    margin: 10px 0;
  }
  .address__juice-bg {
    width: 140px;
    height: 365px;
  }

  hr {
    margin: 40px 0;
  }

  .company {
    gap: 100px;
  }
  .company-info__text {
    font-size: 16px;
  }
  .company-info__title {
    font-size: 16px;
  }
}
@media (max-width: 768px) {
  .contacts {
    padding: 20px 25px;
  }
  .contacts__title {
    font-size: 30px;
    line-height: 55px;
  }
  .contacts__phone {
    font-size: 20px;
    line-height: 30px;
  }
  .contacts__leaflet_bg3 {
    top: -25px;
  }
  .contacts__leaflet_bg2 {
    top: 30px;
  }

  .address__container {
    gap: 35px;
  }

  .ymap {
    height: 400px;
  }
}
@media (max-width: 767px) {
  .contacts__leaflet_bg2 {
    display: none;
  }
  .contacts__leaflet_bg3 {
    display: none;
  }

  .address__juice-bg {
    display: none;
  }
}
@media (max-width: 550px) {
  .contacts {
    padding: 10px 25px;
    margin-bottom: 65px;
  }
  .contacts__title {
    font-size: 24px;
    line-height: 38px;
    margin-bottom: 5px;
  }
  .contacts__phone {
    line-height: 15px;
    font-size: 18px;
  }
  .contacts__text {
    font-size: 14px;
  }
  .contacts__info {
    flex-direction: column;
    gap: 5px;
  }
  .contacts__bg {
    height: 540px;
  }

  .address__title {
    font-size: 20px;
    line-height: 25px;
    margin-bottom: 15px;
  }
  .address__container {
    flex-direction: column;
  }
  .address__text {
    line-height: 18px;
  }
  .address__text_mb {
    margin-bottom: 15px;
  }
  .address__phone {
    font-size: 16px;
    line-height: 20px;
  }

  .company {
    flex-direction: column;
    align-items: flex-start;
    gap: 0;
    margin-bottom: 30px;
  }
  .company-info__text {
    font-size: 14px;
    line-height: 26px;
  }
  .company-info__title {
    font-size: 14px;
    line-height: 26px;
  }

  .ymap {
    height: 280px;
  }
}
@media (max-width: 425px) {
  .contacts {
    padding: 10px 15px;
    margin-bottom: 45px;
  }
  .contacts__bg {
    height: 580px;
  }

  .address {
    padding: 0 15px;
  }

  hr {
    margin: 30px 0;
  }
}
</style>
