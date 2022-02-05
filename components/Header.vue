<template>
  <header class="header">
    <div class="container">
      <div class="header__container">
        <div class="header__left">
          <div class="header__logo-container">
            <nuxt-link to="/"
              ><img src="~/assets/img/logo.png" alt="логотип" class="header__logo"
            /></nuxt-link>
          </div>

          <nav>
            <ol class="header__nav">
              <li class="header__nav-item">
                <nuxt-link class="link" to="/" exact-active-class="link-active"
                  >О компании</nuxt-link
                >
              </li>
              <li class="header__nav-item">
                <nuxt-link class="link" to="/product" exact-active-class="link-active"
                  >Продукция</nuxt-link
                >
              </li>
              <li class="header__nav-item">
                <nuxt-link class="link" to="/contacts" exact-active-class="link-active"
                  >Контакты</nuxt-link
                >
              </li>
            </ol>
          </nav>
        </div>

        <div class="header__right">
          <ol class="header__nav-phone-list">
            <li class="header__nav-phone">
              <a class="link__phone" href="tel:88616265015">8 (86162) 6-50-15</a>
            </li>
            <li class="header__nav-phone">
              <a class="link__phone" href="tel:+79182893779">8 (918) 289-37-79</a>
            </li>
          </ol>
          <a class="header__button" href="#form">Заказать звонок</a>

          <div class="header__burger-container">
            <p class="header__burger-title">Меню</p>

            <div class="header__burger-menu-icon" @click="openBurgerMenu"></div>
          </div>
        </div>
      </div>
    </div>

    <div v-show="isBurgerMenuOpen" class="mobile-menu">
      <transition name="fade" mode="out-in">
        <nav class="mobile-menu__navigation">
          <ul v-show="isBurgerMenuOpen" class="mobile-menu__list">
            <li class="mobile-menu__item mobile-menu__header">
              <h3 class="mobile-menu__title">Меню</h3>
              <div class="mobile-menu__close-btn" @click="closeBurgerMenu"></div>
            </li>

            <li class="mobile-menu__item">
              <nuxt-link class="mobile-menu__link" to="/">О компании</nuxt-link>

              <div v-show="$route.path === '/'" class="mobile-menu__link-active"></div>
            </li>
            <li class="mobile-menu__item">
              <nuxt-link class="mobile-menu__link" to="/product">Продукция</nuxt-link>

              <div v-show="$route.path === '/product'" class="mobile-menu__link-active"></div>
            </li>
            <li class="mobile-menu__item">
              <nuxt-link class="mobile-menu__link" to="/contacts">Контакты</nuxt-link>

              <div v-show="$route.path === '/contacts'" class="mobile-menu__link-active"></div>
            </li>

            <li class="mobile-menu__item mobile-menu__item_column">
              <p class="mobile-menu__description">Мы на связи:</p>
              <a class="mobile-menu__link-phone" href="tel:88616265015">8 (86162) 6-50-15</a>
            </li>
            <li class="mobile-menu__item">
              <a class="mobile-menu__link-phone" href="tel:+79182893779">8 (918) 289-37-79</a>
            </li>
          </ul>
        </nav>
      </transition>
    </div>
  </header>
</template>

<script>
export default {
  name: 'Header',

  data() {
    return {
      isBurgerMenuOpen: false,
    };
  },

  methods: {
    openBurgerMenu() {
      this.isBurgerMenuOpen = true;
    },
    closeBurgerMenu() {
      this.isBurgerMenuOpen = false;
    },
  },
};
</script>

<style scoped lang="scss">
.header-p {
  font-size: 18px;
  font-family: 'Raleway';
}
body {
  background-color: #faf5e9;
}

.section {
  background-color: #faf5e9;
}

.container {
  display: block;
  margin: 0 100px;
}

.link {
  display: inline-block;
  padding: 10px 0;
  line-height: 1.3;
  color: #4b4961;

  background: no-repeat 0 100%;
  background-image: linear-gradient(269.21deg, #ffd25a 0.49%, #ffc52b 100%);
  background-size: 0% 4px;
  transition: background-size 0.8s ease;
  &:hover {
    color: linear-gradient(269.21deg, #ffd25a 0.49%, #ffc52b 100%);
    background-size: 100% 4px;
  }
}

.link__phone {
  color: #4b4961;
  transition: 0.3s;
  &:hover {
    color: black;
  }
}

.link__phone-active {
  color: #ffd25a;
}

.link-active {
  background: no-repeat 0 100%;
  background-image: linear-gradient(269.21deg, #ffd25a 0.49%, #ffc52b 100%);
  background-size: 100% 4px;
}

.header {
  position: relative;
  background-color: #faf4e8;
}
.header__container {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
}

.header__left {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  gap: 80px;
}

.header__right {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  gap: 80px;
}

.header__logo-container {
  background-color: white;
  border-radius: 0px 0px 10px 10px;
  box-shadow: 0 0 10px 0 rgba(0, 0, 0, 0.15);
}

.header__logo {
  width: 186px;
  margin: 18px 24px;
}

.header__nav {
  list-style: none;
}

.header__nav-item {
  font-weight: 400;
  font-size: 22px;
  display: inline; /* Отображать как строчный элемент */
  margin-right: 80px; /* Отступ слева */
}

.header__nav-phone {
  font-weight: 400;
  font-size: 22px;
  list-style: none;
  padding: 3px;
}

.header__button {
  font-family: 'comfortaa';
  text-decoration: none;
  color: #000;
  padding: 20px 43px;
  background: linear-gradient(269.21deg, #ffd25a 0.49%, #ffc52b 100%);
  border-radius: 10px;
  font-size: 20px;
  transition-duration: 0.5s;

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

.header__burger-container {
  display: none;
}
.header__burger-title {
  color: #ffd25a;
  font-family: Raleway;
  font-style: normal;
  font-weight: 500;
  font-size: 16px;
  line-height: 19px;
  margin-right: 16px;
}
.header__burger-menu-icon {
  width: 48px;
  height: 48px;
  background-image: url('~/assets/img/burger_menu.svg');
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
}

.mobile-menu {
  display: none;
}

@media (max-width: 1640px) {
  .header__left {
    gap: 40px;
  }
  .header__nav-item {
    margin-right: 20px;
  }
  .header__right {
    gap: 40px;
  }
}
@media (max-width: 1440px) {
  .container {
    margin: 0 60px;
  }
  .header__logo {
    width: 140px;
    margin: 18px 12px;
  }
  .header__left {
    gap: 20px;
  }
  .header__nav-item {
    font-size: 18px;
    margin-right: 10px;
  }
  .header__right {
    gap: 20px;
  }
  .header__nav-phone {
    font-size: 18px;
  }
  .header__button {
    padding: 20px;
    font-size: 18px;
  }
}
@media (max-width: 1024px) {
  .container {
    margin: 0 25px;
  }
  .header__nav-item {
    font-size: 16px;
    margin-right: 7px;
  }
  .header__nav-phone {
    font-size: 16px;
  }
  .header__button {
    padding: 14px;
    font-size: 16px;
  }
  .header__logo {
    width: 110px;
  }
}
@media (max-width: 1023px) {
  .header__nav {
    display: none;
  }
  .header__nav-phone-list {
    display: none;
  }
  .header__button {
    display: none;
  }

  .header__burger-container {
    display: flex;
    align-items: center;
  }

  .mobile-menu {
    display: block;
    position: absolute;
    top: 0;
    bottom: 0;
    right: 0;
    left: 0;
    width: 100%;
    height: 100vh;
    background-color: rgba(0, 0, 0, 0.3);
    z-index: 1;
  }
  .mobile-menu__navigation {
    position: absolute;
    top: 0;
    right: 0;
    width: 300px;
    height: 500px;
    background-color: #fff;
    border-radius: 0 0 0 5px;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.15);
    z-index: 1;
  }
  .mobile-menu__header {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  .mobile-menu__title {
    font-family: Raleway;
    font-weight: 500;
    font-size: 16px;
    line-height: 19px;
    color: #ffd25a;
  }
  .mobile-menu__description {
    font-family: Raleway;
    font-style: normal;
    font-weight: bold;
    font-size: 16px;
    line-height: 19px;
    color: #4b4961;
    margin: 15px 0;
  }
  .mobile-menu__list {
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 25px 15px 20px 20px;
  }
  .mobile-menu__close-btn {
    width: 48px;
    height: 48px;
    background-image: url('~/assets/img/close_burger_menu.svg');
    background-size: cover;
    background-repeat: no-repeat;
    background-position: center;
    z-index: 2;
  }
  .mobile-menu__item {
    display: flex;
    position: relative;

    &:first-child {
      padding-bottom: 25px;
    }

    &:not(:first-child) {
      padding: 15px 0;
    }

    &:not(:last-child) {
      border-bottom: 1px solid #f7f7f7;
    }
  }
  .mobile-menu__item_column {
    flex-direction: column;
  }
  .mobile-menu__link {
    width: 100%;
    font-family: Raleway;
    font-style: normal;
    font-weight: 500;
    font-size: 16px;
    line-height: 19px;
    color: #4b4961;
  }

  .mobile-menu__link-active {
    position: absolute;
    top: -1px;
    left: -20px;
    content: '';
    width: 3px;
    height: 52px;
    background: linear-gradient(269.21deg, #ffd25a 0.49%, #ffc52b 100%);
    border-radius: 0 5px 5px 0;
  }

  .mobile-menu__link-phone {
    font-family: Raleway;
    font-style: normal;
    font-weight: normal;
    font-size: 16px;
    line-height: 19px;
    font-feature-settings: 'pnum' on, 'lnum' on;
    color: #8e8e8e;
  }
}
@media (max-width: 425px) {
  .container {
    margin: 0 15px;
  }
  .header__logo {
    width: 85px;
  }
  .mobile-menu__navigation {
    width: 254px;
    height: 382px;
  }
  .mobile-menu__item:first-child {
    padding-bottom: 15px;
  }
}
</style>
