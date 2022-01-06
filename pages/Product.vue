<template>
  <main class="main">
    <section class="filter">
      <div class="filter__wave-bg"></div>
      <div class="filter__leaflets-bg_1"></div>
      <div class="filter__leaflets-bg_2"></div>

      <h2 class="filter__title">Наша продукция</h2>

      <ul class="filter__list">
        <li
          v-for="item in containerVolumeFilter"
          :id="item.id"
          :key="item.id"
          class="filter__list-item"
          :class="[
            { filter__list_active: currentJuice.id === item.id },
            { 'filter__list-item_shadow': currentJuice.id === item.id },
          ]"
          @click="selectVariant(item)"
        >
          <div v-show="currentJuice.id === item.id" class="filter__item-border_active"></div>

          <svg
            v-show="item.id === 'pocket'"
            width="34"
            height="68"
            viewBox="0 0 34 68"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <linearGradient id="containerGradient">
              <stop offset="50%" stop-color="#ffc52b" />
              <stop offset="50%" stop-color="#ffd25a" />
            </linearGradient>
            <path
              d="M32.964 1.87782L32.9868 61.2836L28.7504 66.2694L1.20801 64.7718V3.46392"
              stroke="#B9B9B9"
              stroke-width="2"
              stroke-miterlimit="10"
              stroke-linejoin="round"
            />
            <path
              d="M32.964 1.87854L6.18219 1.04231L1.20801 3.46463L28.7504 4.34299"
              stroke="#B9B9B9"
              stroke-width="2"
              stroke-miterlimit="10"
              stroke-linejoin="round"
            />
            <path
              d="M28.75 66.2694V4.34227L32.9635 1.87782L31.1915 8.41388L28.75 4.34227"
              stroke="#B9B9B9"
              stroke-width="2"
              stroke-miterlimit="10"
              stroke-linejoin="round"
            />
          </svg>

          <svg
            v-show="item.id === 'bottleSmall'"
            width="19"
            height="58"
            viewBox="0 0 19 58"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M13.8162 6.6777C14.0714 8.00638 14.1601 8.17835 14.8081 9.15223C15.4562 10.1261 17.2319 12.3581 17.2319 15.5639C17.2319 18.7698 17.2319 22.7377 17.2319 23.4056C17.2319 25.2376 16.278 25.8295 16.278 26.4196C16.278 27.0097 16.7938 27.4116 16.64 29.1295C16.4879 30.8473 15.8001 36.2471 16.278 40.2531C16.7558 44.259 17.0599 46.3208 17.0418 48.3428C17.0219 50.3648 16.9368 52.6022 15.8164 53.7516C15.8164 53.7516 15.5358 54.2096 15.4055 54.4956C15.277 54.7816 14.2416 55.6921 13.1157 55.7935C13.1157 55.7935 12.7428 55.808 12.5292 55.7175C12.5292 55.7175 12.4532 55.8895 12.2287 56.0125C12.0043 56.1356 10.2213 56.3854 9.20767 56.1556C8.19401 56.3836 6.41105 56.1356 6.18659 56.0125C5.96214 55.8895 5.88612 55.7175 5.88612 55.7175C5.67071 55.808 5.29964 55.7935 5.29964 55.7935C4.17375 55.694 3.13837 54.7816 3.00985 54.4956C2.88133 54.2096 2.59896 53.7516 2.59896 53.7516C1.4785 52.6022 1.39161 50.3648 1.37351 48.3428C1.3536 46.3208 1.65951 44.259 2.13738 40.2531C2.61525 36.2471 1.92741 30.8473 1.77536 29.1295C1.62331 27.4116 2.13738 27.0115 2.13738 26.4196C2.13738 25.8277 1.18164 25.2376 1.18164 23.4056C1.18164 22.7377 1.18164 18.7698 1.18164 15.5639C1.18164 12.3581 2.95555 10.1261 3.60538 9.15223C4.25521 8.17835 4.3439 8.00819 4.59732 6.6777L4.69325 5.2024V4.9544L4.22987 4.82045C4.22987 4.82045 3.86784 1.43721 4.56655 1.258C5.26525 1.07879 9.22034 1.0625 9.22034 1.0625H9.19319C9.19319 1.0625 13.1483 1.08241 13.8488 1.25981C14.5475 1.43721 14.1855 4.78243 14.1855 4.78243L13.7221 4.9544V5.2024L13.8162 6.6777Z"
              stroke="#B9B9B9"
              stroke-width="2"
              stroke-miterlimit="10"
            />
            <path
              d="M2.13477 26.4189C2.13477 26.4189 4.4861 27.2625 9.20687 27.2625C13.9276 27.2625 16.279 26.4189 16.279 26.4189"
              stroke="#B9B9B9"
              stroke-width="2"
              stroke-miterlimit="10"
            />
            <path
              d="M4.69067 4.9541C4.69067 4.9541 5.70615 5.34148 9.20509 5.34148C12.704 5.34148 13.7195 4.9541 13.7195 4.9541"
              stroke="#B9B9B9"
              stroke-width="2"
              stroke-miterlimit="10"
            />
          </svg>

          <svg
            v-show="item.id === 'bottleMiddle'"
            width="35"
            height="75"
            viewBox="0 0 35 75"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M17.1924 73.3877C17.1924 73.3877 20.5896 73.3462 21.37 73.2765C22.1504 73.2069 22.9575 72.7656 22.9575 72.7656C22.9575 72.7656 23.041 72.973 23.9317 73.1389C24.8223 73.3047 27.1617 73.1389 29.6683 72.6412C32.1748 72.1436 33.0654 68.4944 33.0654 66.061C33.0654 63.6276 33.2142 30.9884 33.0654 24.647C32.9167 18.3056 21.9064 11.3223 21.9064 11.3223C22.2222 11.1382 22.2406 10.8247 22.2406 10.8247V9.57064V8.46425L21.3499 8.11426C21.3499 8.11426 21.3499 6.52849 21.2196 5.73727C21.0893 4.94605 18.1382 4.88965 17.1908 4.88965C16.2433 4.88965 13.2923 4.94439 13.1619 5.73727C13.0316 6.53015 13.0316 8.11426 13.0316 8.11426L12.141 8.46425V9.57064V10.8247C12.141 10.8247 12.1593 11.1382 12.4752 11.3223C12.4752 11.3223 1.46482 18.3073 1.3161 24.647C1.16738 30.9867 1.3161 63.6276 1.3161 66.061C1.3161 68.4944 2.20675 72.1436 4.71328 72.6412C7.21981 73.1389 9.55923 73.3047 10.4499 73.1389C11.3405 72.973 11.4241 72.7656 11.4241 72.7656C11.4241 72.7656 12.2312 73.2085 13.0116 73.2765C13.7936 73.3462 17.1924 73.3877 17.1924 73.3877Z"
              stroke="#B9B9B9"
              stroke-width="2"
              stroke-miterlimit="10"
            />
            <path
              d="M12.4749 11.3238C12.4749 11.3238 14.8327 11.085 17.1905 11.085C19.5483 11.085 21.9061 11.3238 21.9061 11.3238"
              stroke="#B9B9B9"
              stroke-width="2"
              stroke-miterlimit="10"
            />
            <path
              d="M22.2141 11.0834H12.1696C11.6516 11.0834 11.2322 10.6671 11.2322 10.1529V4.64749C11.2322 3.14301 12.4604 1.92383 13.976 1.92383H20.4094C21.925 1.92383 23.1532 3.14301 23.1532 4.64749V10.1529C23.1516 10.6671 22.7321 11.0834 22.2141 11.0834Z"
              stroke="#B9B9B9"
              stroke-width="2"
              stroke-miterlimit="10"
            />
            <path
              d="M1.31787 24.6484C1.31787 24.6484 7.96518 25.3302 17.1925 25.3302C26.4199 25.3302 33.0672 24.6484 33.0672 24.6484"
              stroke="#B9B9B9"
              stroke-width="2"
              stroke-miterlimit="10"
            />
            <path
              d="M1.31787 66.0625C1.31787 66.0625 6.92581 66.7442 17.1925 66.7442C27.4593 66.7442 33.0672 66.0625 33.0672 66.0625"
              stroke="#B9B9B9"
              stroke-width="2"
              stroke-miterlimit="10"
            />
          </svg>

          <svg
            v-show="item.id === 'bottleBig'"
            width="42"
            height="83"
            viewBox="0 0 42 83"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M20.8652 81.3804C20.8652 81.3804 25.0439 81.3339 26.0042 81.2563C26.9628 81.1788 27.9576 80.6824 27.9576 80.6824C27.9576 80.6824 28.0608 80.9151 29.1571 81.1012C30.2534 81.2873 33.131 81.1012 36.2133 80.5428C39.2957 79.9844 40.392 75.8844 40.392 73.1511C40.392 70.4178 40.5744 33.7504 40.392 26.6275C40.2096 19.5046 26.6668 11.6579 26.6668 11.6579C27.0557 11.4511 27.0781 11.0995 27.0781 11.0995V9.6915V8.44892L25.9818 8.05598C25.9818 8.05598 25.9818 6.27569 25.8218 5.38469C25.6617 4.49368 22.0303 4.43164 20.8652 4.43164C19.7001 4.43164 16.0687 4.49368 15.9086 5.38469C15.7486 6.27569 15.7486 8.05598 15.7486 8.05598L14.6523 8.44892V9.6915V11.0995C14.6523 11.0995 14.6747 11.4511 15.0636 11.6579C15.0636 11.6579 1.52083 19.5046 1.3384 26.6275C1.15597 33.7504 1.3384 70.4178 1.3384 73.1511C1.3384 75.8844 2.4347 79.9844 5.51706 80.5428C8.59942 81.1012 11.477 81.2873 12.5733 81.1012C13.6696 80.9151 13.7728 80.6824 13.7728 80.6824C13.7728 80.6824 14.7659 81.1788 15.7262 81.2563C16.6865 81.3339 20.8652 81.3804 20.8652 81.3804Z"
              stroke="#B9B9B9"
              stroke-width="2"
              stroke-miterlimit="10"
            />
            <path
              d="M15.064 11.6575C15.064 11.6575 17.9639 11.3887 20.8656 11.3887C23.7672 11.3887 26.6671 11.6575 26.6671 11.6575"
              stroke="#B9B9B9"
              stroke-width="2"
              stroke-miterlimit="10"
            />
            <path
              d="M27.2316 11.3891H14.4994C13.9659 11.3891 13.5339 10.9566 13.5339 10.4223V3.92848C13.5339 2.36534 14.7989 1.09863 16.3599 1.09863H25.3712C26.9321 1.09863 28.1971 2.36534 28.1971 3.92848V10.4223C28.1971 10.9566 27.7651 11.3891 27.2316 11.3891Z"
              stroke="#B9B9B9"
              stroke-width="2"
              stroke-miterlimit="10"
            />
            <path
              d="M1.33862 26.627C1.33862 26.627 9.51523 27.3939 20.8654 27.3939C32.2156 27.3939 40.3922 26.627 40.3922 26.627"
              stroke="#B9B9B9"
              stroke-width="2"
              stroke-miterlimit="10"
            />
            <path
              d="M1.33862 73.1514C1.33862 73.1514 8.23651 73.9183 20.8654 73.9183C33.4943 73.9183 40.3922 73.1514 40.3922 73.1514"
              stroke="#B9B9B9"
              stroke-width="2"
              stroke-miterlimit="10"
            />
          </svg>

          <div class="filter__item-info">
            <span class="filter__item-juice-volume">{{ item.volume }}</span>
            <span class="filter__item-juice-container">{{ item.container }}</span>
          </div>
        </li>
      </ul>

      <ul class="filter__list_second">
        <li
          v-for="item in filterValueSecond"
          :key="item.id"
          class="filter__item_second"
          :class="{ filter__item_second_active: currentSecondFilter === item.name }"
          @click="currentSecondFilter = item.name"
        >
          <span class="filter__item-name">
            {{ item.name }}
          </span>
        </li>
      </ul>
    </section>
  </main>
</template>

<script>
const containerVolumeFilter = [
  {
    id: 'pocket',
    volume: '1л',
    container: 'Пакет',
  },
  {
    id: 'bottleSmall',
    volume: '0,5л',
    container: 'Бутылка',
  },
  {
    id: 'bottleMiddle',
    volume: '3л',
    container: 'Бутылка',
  },
  {
    id: 'bottleBig',
    volume: '5л',
    container: 'Бутылка',
  },
];
const filterValueSecond = [
  {
    id: 1,
    name: 'Сок тетра пакет 1л',
  },
  {
    id: 2,
    name: 'Напитки «Прогулка по саду» 0,5л',
  },
  {
    id: 3,
    name: 'Напитки «Прогулка по саду» 1л',
  },
];
export default {
  name: 'Product',

  data() {
    return {
      containerVolumeFilter: [...containerVolumeFilter],
      filterValueSecond: [...filterValueSecond],

      currentJuice: {},
      currentSecondFilter: '',
    };
  },

  head: {
    title: 'Продукты',
  },

  methods: {
    selectVariant(item) {
      this.currentJuice = item;
    },
  },
};
</script>

<style lang="scss" scoped>
$primaryFontColor: #4b4961;
.main {
  font-family: Montserrat Alternates;
}
.filter {
  position: relative;

  height: 588px;

  overflow: hidden;
  margin-bottom: 50px;
  padding: 100px 60px 0;
}
.filter__wave-bg {
  position: absolute;
  top: -144px;
  left: 0;
  right: 0;
  bottom: 0;

  background-image: url('~/assets/img/wave_bg.svg');
  background-size: cover;
  background-position: center;
  background-repeat: repeat-x;

  z-index: -1;
}
.filter__leaflets-bg_1 {
  position: absolute;
  top: 129px;
  right: -104px;

  width: 428px;
  height: 127px;

  background-image: url('~/assets/img/leaflet_1.svg');
  background-size: auto;
  background-position: center;
  background-repeat: no-repeat;
}
.filter__leaflets-bg_2 {
  position: absolute;
  top: 212px;
  right: 194px;

  width: 285px;
  height: 114px;

  background-image: url('~/assets/img/leaflet_2.svg');
  background-size: auto;
  background-position: center;
  background-repeat: no-repeat;
}
.filter__title {
  font-weight: bold;
  font-size: 72px;
  line-height: 87px;
  color: $primaryFontColor;
}

.filter__list {
  display: flex;
  flex-wrap: wrap;
  gap: 30px;

  margin-top: 53px;

  &_active {
    path {
      stroke: url(#containerGradient);
    }
  }
}
.filter__item-border_active {
  position: absolute;
  left: 0;

  width: 5px;
  height: 86px;

  background: linear-gradient(269.21deg, #ffd25a 0.49%, #ffc52b 100%);
  border-radius: 0 5px 5px 0;
}
#pocket {
  position: relative;
}
#bottleSmall {
  position: relative;
}
#bottleMiddle {
  position: relative;
}
#bottleBig {
  position: relative;
}
.filter__list-item {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 19px;

  width: 220px;
  height: 106px;

  background-color: #fff;
  border-radius: 6px;

  cursor: pointer;
}
.filter__list-item_shadow {
  box-shadow: 0 4px 17px rgba(159, 159, 159, 0.2);
}
.filter__item-wrap {
  display: flex;
  justify-content: center;
  height: 106px;
  width: 220px;
}
.filter__item-container {
  display: flex;
  align-items: center;
  gap: 19px;
}
.filter__item-info {
  display: flex;
  flex-direction: column;
}
.filter__item-juice-volume {
  font-family: Raleway;
  font-size: 30px;
  font-weight: bold;
  line-height: 37px;
  color: $primaryFontColor;
  font-feature-settings: 'pnum' on, 'lnum' on;
}
.filter__item-juice-container {
  font-family: Raleway;
  font-size: 22px;
  line-height: 27px;
  color: $primaryFontColor;
  font-feature-settings: 'pnum' on, 'lnum' on;
}

.filter__list_second {
  display: flex;
  gap: 35px;

  margin-top: 76px;
}
.filter__item_second {
  background-color: #fff;
  border-radius: 10px;

  padding: 20px 26px;

  cursor: pointer;
  transition: all 0.6s;
  box-shadow: 0 4px 17px rgba(159, 159, 159, 0.2);

  &_active {
    background: linear-gradient(269.21deg, #ffd25a 0.49%, #ffc52b 100%);
    span {
      color: #fff;
    }
  }
}
.filter__item-name {
  font-family: Rubik;
  font-style: normal;
  font-weight: 500;
  font-size: 24px;
  line-height: 28px;

  color: #525252;
}
</style>
