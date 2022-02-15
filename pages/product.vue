<template>
  <main class="main">
    <section class="filter">
      <div class="filter__wave-bg"></div>
      <div class="filter__leaflets-bg_1"></div>
      <div class="filter__leaflets-bg_2"></div>

      <h2 class="filter__title">Наша продукция</h2>

      <ul class="filter__list">
        <li
          v-for="item in volumeFilters"
          :id="item.id"
          :key="item.id"
          class="filter__list-item"
          :class="{ filter__list_active: filterByVolume.id === item.id }"
          @click="selectVolume(item)"
        >
          <div v-show="filterByVolume.id === item.id" class="filter__item-border_active"></div>

          <svg
            v-show="item.id === 'bottleSmall_1'"
            width="24"
            height="75"
            viewBox="0 0 24 75"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <linearGradient id="containerGradient">
              <stop offset="50%" stop-color="#ffc52b" />
              <stop offset="50%" stop-color="#ffd25a" />
            </linearGradient>
            <path
              d="M18.1793 8.61799C18.5214 10.3641 18.6403 10.5901 19.509 11.8699C20.3776 13.1497 22.7579 16.0828 22.7579 20.2958C22.7579 24.5088 22.7579 29.7232 22.7579 30.601C22.7579 33.0084 21.4792 33.7863 21.4792 34.5618C21.4792 35.3373 22.1707 35.8654 21.9645 38.123C21.7606 40.3805 20.8386 47.4766 21.4792 52.741C22.1197 58.0054 22.5274 60.715 22.5031 63.3722C22.4764 66.0293 22.3624 68.9696 20.8605 70.4802C20.8605 70.4802 20.4844 71.082 20.3097 71.4579C20.1374 71.8337 18.7495 73.0303 17.2403 73.1635C17.2403 73.1635 16.7405 73.1826 16.4541 73.0636C16.4541 73.0636 16.3522 73.2896 16.0514 73.4514C15.7505 73.6131 13.3605 73.9414 12.0017 73.6393C10.643 73.939 8.25298 73.6131 7.95211 73.4514C7.65124 73.2896 7.54933 73.0636 7.54933 73.0636C7.26059 73.1826 6.76318 73.1635 6.76318 73.1635C5.25397 73.0327 3.86608 71.8337 3.69381 71.4579C3.52154 71.082 3.14302 70.4802 3.14302 70.4802C1.64109 68.9696 1.52462 66.0293 1.50036 63.3722C1.47367 60.715 1.88373 58.0054 2.52429 52.741C3.16486 47.4766 2.24283 40.3805 2.03902 38.123C1.8352 35.8654 2.52429 35.3397 2.52429 34.5618C2.52429 33.7839 1.24316 33.0084 1.24316 30.601C1.24316 29.7232 1.24316 24.5088 1.24316 20.2958C1.24316 16.0828 3.62102 13.1497 4.49209 11.8699C5.36316 10.5901 5.48205 10.3664 5.82175 8.61799L5.95034 6.67922V6.35331L5.32919 6.17728C5.32919 6.17728 4.84391 1.73119 5.7805 1.49569C6.71708 1.26018 12.0187 1.23877 12.0187 1.23877H11.9823C11.9823 1.23877 17.284 1.26494 18.223 1.49806C19.1596 1.73119 18.6743 6.12732 18.6743 6.12732L18.0531 6.35331V6.67922L18.1793 8.61799Z"
              stroke="#B9B9B9"
              stroke-width="2"
              stroke-miterlimit="10"
            />
            <path
              d="M2.52148 34.561C2.52148 34.561 5.67335 35.6696 12.0014 35.6696C18.3294 35.6696 21.4812 34.561 21.4812 34.561"
              stroke="#B9B9B9"
              stroke-width="2"
              stroke-miterlimit="10"
            />
            <path
              d="M5.94727 6.35254C5.94727 6.35254 7.30847 6.86162 11.9987 6.86162C16.6889 6.86162 18.0501 6.35254 18.0501 6.35254"
              stroke="#B9B9B9"
              stroke-width="2"
              stroke-miterlimit="10"
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
          v-for="item in typeFilters"
          :key="item.id"
          class="filter__item_second"
          :class="{ filter__item_second_active: filterByType.name === item.name }"
          @click="selectType(item)"
        >
          <span class="filter__item-name">
            {{ item.name }}
          </span>
        </li>

        <li
          v-show="filterByVolume.id === 'bottleMiddle'"
          class="filter__item_second"
          :class="{ filter__item_second_active: filterByType.name === 'Сиропы' }"
          @click="selectSyrupType"
        >
          <span class="filter__item-name"> Сиропы </span>
        </li>
      </ul>

      <div class="filter__container_mobile">
        <div class="filter-dropdown" :class="{ 'filter-dropdown_opened': isVolumeFilterOpened }">
          <button class="filter-dropdown__toggle" @click="toggleVolumeFilter">
            <span> {{ filterByVolume.value }} л </span>

            <span class="filter-dropdown__icon"></span>
          </button>

          <transition name="fade" mode="out-in">
            <div v-if="isVolumeFilterOpened" class="filter-dropdown__menu" role="listbox">
              <button
                v-for="item in volumeFilters"
                :id="item.id"
                :key="item.id"
                class="filter-dropdown__item"
                @click="selectVolume(item)"
              >
                {{ item.volume }} {{ item.container }}
              </button>
            </div>
          </transition>
        </div>

        <div class="filter-dropdown" :class="{ 'filter-dropdown_opened': isTypeFilterOpened }">
          <button
            class="filter-dropdown__toggle filter-dropdown__toggle_second"
            @click="isTypeFilterOpened = !isTypeFilterOpened"
          >
            <span> {{ filterByType.name }} </span>

            <span class="filter-dropdown__icon filter-dropdown__icon_second"></span>
          </button>
          <transition name="fade" mode="out-in">
            <div
              v-if="isTypeFilterOpened"
              class="filter-dropdown__menu filter-dropdown__menu_second"
              role="listbox"
            >
              <button
                v-for="item in typeFilters"
                :id="item.id"
                :key="item.id"
                class="filter-dropdown__item filter-dropdown__item_second"
                @click="selectType(item)"
              >
                {{ item.name }}
              </button>

              <button
                v-if="filterByVolume.id === 'bottleMiddle'"
                class="filter-dropdown__item filter-dropdown__item_second"
                @click="selectSyrupType"
              >
                Сиропы
              </button>
            </div>
          </transition>
        </div>
      </div>

      <div class="slider__container_mobile">
        <swiper ref="swiper" class="swiper" :options="swiperOption">
          <swiper-slide
            v-for="(juice, index) in sortingJuicesByType"
            :key="juice.id"
            :class="{ 'juice-miniature_active': currentJuiceMiniature === juice }"
            @click.native="currentJuiceMiniature = juice"
          >
            <SliderJuiceMiniature
              :juice-miniature="juice.slideMiniature"
              :juice-tooltip="juice.tooltip"
              @chooseSlide="chooseSlide(juice, index)"
            />
          </swiper-slide>
        </swiper>

        <div class="button-prev" @mousedown.prevent.stop>
          <svg
            width="27"
            height="17"
            viewBox="0 0 27 17"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M11.3121 1.33199C12.4972 0.0688275 14.5028 0.068826 15.6879 1.33198L25.6471 11.9474C27.4445 13.8631 26.0861 17 23.4593 17H3.54071C0.913862 17 -0.444463 13.8631 1.35285 11.9474L11.3121 1.33199Z"
              fill="#C4C4C4"
            />
          </svg>
        </div>

        <div class="button-next" @mousedown.prevent.stop>
          <svg
            width="27"
            height="17"
            viewBox="0 0 27 17"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M11.3121 15.668C12.4972 16.9312 14.5028 16.9312 15.6879 15.668L25.6471 5.05264C27.4445 3.13692 26.0861 0 23.4593 0H3.54071C0.913862 0 -0.444463 3.13691 1.35285 5.05263L11.3121 15.668Z"
              fill="#C4C4C4"
            />
          </svg>
        </div>
      </div>
    </section>

    <section class="slider">
      <div class="slider__container">
        <swiper ref="swiper" class="swiper" :options="swiperOption">
          <swiper-slide
            v-for="(juice, index) in sortingJuicesByType"
            :key="juice.id"
            :class="{ 'juice-miniature_active': currentJuiceMiniature === juice }"
            @click.native="currentJuiceMiniature = juice"
          >
            <SliderJuiceMiniature
              :juice-miniature="juice.slideMiniature"
              :juice-tooltip="juice.tooltip"
              @chooseSlide="chooseSlide(juice, index)"
            />
          </swiper-slide>
        </swiper>

        <div class="button-prev" @mousedown.prevent.stop>
          <svg
            width="27"
            height="17"
            viewBox="0 0 27 17"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M11.3121 1.33199C12.4972 0.0688275 14.5028 0.068826 15.6879 1.33198L25.6471 11.9474C27.4445 13.8631 26.0861 17 23.4593 17H3.54071C0.913862 17 -0.444463 13.8631 1.35285 11.9474L11.3121 1.33199Z"
              fill="#C4C4C4"
            />
          </svg>
        </div>

        <div class="button-next" @mousedown.prevent.stop>
          <svg
            width="27"
            height="17"
            viewBox="0 0 27 17"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M11.3121 15.668C12.4972 16.9312 14.5028 16.9312 15.6879 15.668L25.6471 5.05264C27.4445 3.13692 26.0861 0 23.4593 0H3.54071C0.913862 0 -0.444463 3.13691 1.35285 5.05263L11.3121 15.668Z"
              fill="#C4C4C4"
            />
          </svg>
        </div>
      </div>

      <div class="slider__tooltip_mobile">
        <span>{{ chosenJuice.tooltip }}</span>
      </div>

      <ChosenJuiceDetailInfo :juice="chosenJuice" />

      <div class="slider__bottom-bg">
        <svg
          width="100%"
          height="1353"
          viewBox="0 0 1920 1353"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <ellipse cx="962" cy="1165.5" rx="2809" ry="1165.5" fill="#FFFCF3" />
        </svg>
      </div>
    </section>
  </main>
</template>

<script>
import { Swiper, SwiperSlide } from 'vue-awesome-swiper';
import 'swiper/css/swiper.css';
import SliderJuiceMiniature from '~/components/SliderJuiceMiniature';
import ChosenJuiceDetailInfo from '~/components/ChosenJuiceDetailInfo';

const volumeFilters = [
  {
    id: 'bottleSmall_1',
    value: '1',
    volume: '1л',
    container: 'Бутылка',
  },
  {
    id: 'bottleSmall',
    value: '0,5',
    volume: '0,5л',
    container: 'Бутылка',
  },
  {
    id: 'bottleMiddle',
    value: '3',
    volume: '3л',
    container: 'Бутылка',
  },
  {
    id: 'bottleBig',
    value: '5',
    volume: '5л',
    container: 'Бутылка',
  },
];
const typeFilters = [
  {
    id: 1,
    name: 'Напитки',
    type: 'juice',
  },
  {
    id: 2,
    name: 'Узвары',
    type: 'uzvar',
  },
];
export default {
  name: 'Product',

  components: {
    Swiper,
    SwiperSlide,
    SliderJuiceMiniature,
    ChosenJuiceDetailInfo,
  },

  data() {
    return {
      volumeFilters: [...volumeFilters],
      typeFilters: [...typeFilters],
      // 39 элементов
      juices: [
        // соки
        // апельсин
        {
          id: 1,
          type: 'juice',
          volume: '0,5',
          tooltip: 'Апельсин',
          name: '0.5 л НАПИТОК безалкогольный НЕГАЗИРОВАННЫЙ неосветленный СО ВКУСОМ АПЕЛЬСИНА',
          description: ``,
          benefit: 'Калий, входящий в состав напитка, помогает укрепить сердце и укрепляет сосуды.',
          macronutrients: [
            {
              name: 'Калории',
              value: '9 ккал/ 37,8 кДж.',
            },
            {
              name: 'Углеводы',
              value: '– 2 (± 0,2) г',
            },
          ],
          composition: {
            main: 'вода питьевая, сахарный сироп, сок яблочный, регулятор кислотности лимонная кислота, ароматизатор пищевой «Апельсин», подсластитель «Мультисвит 200F», аскорбиновая кислота, консерванты (сорбат калия, бензоат  натрия)',
          },
          microelements: [
            {
              element: 'А,С',
            },
            {
              element: 'К,В',
            },
            {
              element: 'β- каротин',
            },
          ],
          energyValue: '9 ккал/ 37,8 кДж',
          image: 'orange_05',
          fruitImage: 'orange',
          slideMiniature: 'orange',
        },
        {
          id: 2,
          type: 'juice',
          volume: '1',
          tooltip: 'Апельсин',
          name: '1 л НАПИТОК безалкогольный НЕГАЗИРОВАННЫЙ неосветленный СО ВКУСОМ АПЕЛЬСИНА',
          description: ``,
          benefit: 'Калий, входящий в состав напитка, помогает укрепить сердце и укрепляет сосуды.',
          macronutrients: [
            {
              name: 'Калории',
              value: '9 ккал/ 37,8 кДж.',
            },
            {
              name: 'Углеводы',
              value: '– 2 (± 0,2) г',
            },
          ],
          composition: {
            main: 'вода питьевая, сахарный сироп, сок яблочный, регулятор кислотности лимонная кислота, ароматизатор пищевой «Апельсин», подсластитель «Мультисвит 200F», аскорбиновая кислота, консерванты (сорбат калия, бензоат  натрия)',
          },
          microelements: [
            {
              element: 'А,С',
            },
            {
              element: 'К,В',
            },
            {
              element: 'β- каротин',
            },
          ],
          energyValue: '9 ккал/ 37,8 кДж',
          image: 'orange_1',
          fruitImage: 'orange',
          slideMiniature: 'orange',
        },
        {
          id: 3,
          type: 'juice',
          volume: '3',
          tooltip: 'Апельсин',
          name: '3 л НАПИТОК безалкогольный НЕГАЗИРОВАННЫЙ неосветленный СО ВКУСОМ АПЕЛЬСИНА',
          description: ``,
          benefit: 'Калий, входящий в состав напитка, помогает укрепить сердце и укрепляет сосуды.',
          macronutrients: [
            {
              name: 'Калории',
              value: '9 ккал/ 37,8 кДж.',
            },
            {
              name: 'Углеводы',
              value: '– 2 (± 0,2) г',
            },
          ],
          composition: {
            main: 'вода питьевая, сахарный сироп, сок яблочный, регулятор кислотности лимонная кислота, ароматизатор пищевой «Апельсин», подсластитель «Мультисвит 200F», аскорбиновая кислота, консерванты (сорбат калия, бензоат  натрия)',
          },
          microelements: [
            {
              element: 'А,С',
            },
            {
              element: 'К,В',
            },
            {
              element: 'β- каротин',
            },
          ],
          energyValue: '9 ккал/ 37,8 кДж',
          image: 'orange_3',
          fruitImage: 'orange',
          slideMiniature: 'orange',
        },
        {
          id: 4,
          type: 'juice',
          volume: '5',
          tooltip: 'Апельсин',
          name: '5 л НАПИТОК безалкогольный НЕГАЗИРОВАННЫЙ неосветленный СО ВКУСОМ АПЕЛЬСИНА',
          description: ``,
          benefit: 'Калий, входящий в состав напитка, помогает укрепить сердце и укрепляет сосуды.',
          macronutrients: [
            {
              name: 'Калории',
              value: '9 ккал/ 37,8 кДж.',
            },
            {
              name: 'Углеводы',
              value: '– 2 (± 0,2) г',
            },
          ],
          composition: {
            main: 'вода питьевая, сахарный сироп, сок яблочный, регулятор кислотности лимонная кислота, ароматизатор пищевой «Апельсин», подсластитель «Мультисвит 200F», аскорбиновая кислота, консерванты (сорбат калия, бензоат  натрия)',
          },
          microelements: [
            {
              element: 'А,С',
            },
            {
              element: 'К,В',
            },
            {
              element: 'β- каротин',
            },
          ],
          energyValue: '9 ккал/ 37,8 кДж',
          image: 'orange_5',
          fruitImage: 'orange',
          slideMiniature: 'orange',
        },
        // абрикос
        {
          id: 5,
          type: 'juice',
          volume: '0,5',
          tooltip: 'Абрикос',
          name: '0.5 л НАПИТОК безалкогольный НЕГАЗИРОВАННЫЙ неосветленный СО ВКУСОМ АБРИКОСА',
          description: ``,
          benefit: 'Калий, входящий в состав напитка, помогает укрепить сердце и укрепляет сосуды.',
          macronutrients: [
            {
              name: 'Калории',
              value: '9 ккал/ 37,8 кДж.',
            },
            {
              name: 'Углеводы',
              value: '– 2 (± 0,2) г',
            },
          ],
          composition: {
            main: 'вода питьевая, сахарный сироп, сок яблочный, регулятор кислотности лимонная кислота, ароматизатор пищевой «Абрикос», подсластитель «Мультисвит 200F», аскорбиновая кислота, консерванты (сорбат калия, бензоат  натрия)',
          },
          microelements: [
            {
              element: 'А,С',
            },
            {
              element: 'К,В',
            },
            {
              element: 'β- каротин',
            },
          ],
          energyValue: '9 ккал/ 37,8 кДж',
          image: 'apricot_05',
          fruitImage: 'apricot',
          slideMiniature: 'apricot',
        },
        {
          id: 6,
          type: 'juice',
          volume: '1',
          tooltip: 'Абрикос',
          name: '1 л НАПИТОК безалкогольный НЕГАЗИРОВАННЫЙ неосветленный СО ВКУСОМ АБРИКОСА',
          description: ``,
          benefit: 'Калий, входящий в состав напитка, помогает укрепить сердце и укрепляет сосуды.',
          macronutrients: [
            {
              name: 'Калории',
              value: '9 ккал/ 37,8 кДж.',
            },
            {
              name: 'Углеводы',
              value: '– 2 (± 0,2) г',
            },
          ],
          composition: {
            main: 'вода питьевая, сахарный сироп, сок яблочный, регулятор кислотности лимонная кислота, ароматизатор пищевой «Абрикос», подсластитель «Мультисвит 200F», аскорбиновая кислота, консерванты (сорбат калия, бензоат  натрия)',
          },
          microelements: [
            {
              element: 'А,С',
            },
            {
              element: 'К,В',
            },
            {
              element: 'β- каротин',
            },
          ],
          energyValue: '9 ккал/ 37,8 кДж',
          image: 'apricot_1',
          fruitImage: 'apricot',
          slideMiniature: 'apricot',
        },
        {
          id: 7,
          type: 'juice',
          volume: '3',
          tooltip: 'Абрикос',
          name: '3 л НАПИТОК безалкогольный НЕГАЗИРОВАННЫЙ неосветленный СО ВКУСОМ АБРИКОСА',
          description: ``,
          benefit: 'Калий, входящий в состав напитка, помогает укрепить сердце и укрепляет сосуды.',
          macronutrients: [
            {
              name: 'Калории',
              value: '9 ккал/ 37,8 кДж.',
            },
            {
              name: 'Углеводы',
              value: '– 2 (± 0,2) г',
            },
          ],
          composition: {
            main: 'вода питьевая, сахарный сироп, сок яблочный, регулятор кислотности лимонная кислота, ароматизатор пищевой «Абрикос», подсластитель «Мультисвит 200F», аскорбиновая кислота, консерванты (сорбат калия, бензоат  натрия)',
          },
          microelements: [
            {
              element: 'А,С',
            },
            {
              element: 'К,В',
            },
            {
              element: 'β- каротин',
            },
          ],
          energyValue: '9 ккал/ 37,8 кДж',
          image: 'apricot_3',
          fruitImage: 'apricot',
          slideMiniature: 'apricot',
        },
        {
          id: 8,
          type: 'juice',
          volume: '5',
          tooltip: 'Абрикос',
          name: '5 л НАПИТОК безалкогольный НЕГАЗИРОВАННЫЙ неосветленный СО ВКУСОМ АБРИКОСА',
          description: ``,
          benefit: 'Калий, входящий в состав напитка, помогает укрепить сердце и укрепляет сосуды.',
          macronutrients: [
            {
              name: 'Калории',
              value: '9 ккал/ 37,8 кДж.',
            },
            {
              name: 'Углеводы',
              value: '– 2 (± 0,2) г',
            },
          ],
          composition: {
            main: 'вода питьевая, сахарный сироп, сок яблочный, регулятор кислотности лимонная кислота, ароматизатор пищевой «Абрикос», подсластитель «Мультисвит 200F», аскорбиновая кислота, консерванты (сорбат калия, бензоат  натрия)',
          },
          microelements: [
            {
              element: 'А,С',
            },
            {
              element: 'К,В',
            },
            {
              element: 'β- каротин',
            },
          ],
          energyValue: '9 ккал/ 37,8 кДж',
          image: 'apricot_5',
          fruitImage: 'apricot',
          slideMiniature: 'apricot',
        },
        // гранат
        {
          id: 9,
          type: 'juice',
          volume: '1',
          tooltip: 'Гранат',
          name: '1 л НАПИТОК безалкогольный НЕГАЗИРОВАННЫЙ ОСВЕТЛЕННЫЙ СО ВКУСОМ ГРАНАТА',
          description: ``,
          benefit: 'Калий, входящий в состав напитка, помогает укрепить сердце и укрепляет сосуды.',
          macronutrients: [
            {
              name: 'Калории',
              value: '9 ккал/ 37,8 кДж.',
            },
            {
              name: 'Углеводы',
              value: '– 2 (± 0,2) г',
            },
          ],
          composition: {
            main: 'вода питьевая, сахарный сироп, сок яблочный ,регулятор кислотности лимонная кислота, ароматизатор пищевой «Гранат», подсластитель «Мультисвит 200F», красители -  морковный сок,  сахарный колер Е 150d, консерванты (сорбат калия, бензоат  натрия)',
          },
          microelements: [
            {
              element: 'E,P',
            },
            {
              element: 'B,C',
            },
          ],
          energyValue: '9 ккал/ 37,8 кДж',
          image: 'garnet_1',
          fruitImage: 'garnet',
          slideMiniature: 'garnet',
        },
        {
          id: 10,
          type: 'juice',
          volume: '3',
          tooltip: 'Гранат',
          name: '3 л НАПИТОК безалкогольный НЕГАЗИРОВАННЫЙ ОСВЕТЛЕННЫЙ СО ВКУСОМ ГРАНАТА',
          description: ``,
          benefit: 'Калий, входящий в состав напитка, помогает укрепить сердце и укрепляет сосуды.',
          macronutrients: [
            {
              name: 'Калории',
              value: '9 ккал/ 37,8 кДж.',
            },
            {
              name: 'Углеводы',
              value: '– 2 (± 0,2) г',
            },
          ],
          composition: {
            main: 'вода питьевая, сахарный сироп, сок яблочный ,регулятор кислотности лимонная кислота, ароматизатор пищевой «Гранат», подсластитель «Мультисвит 200F», красители -  морковный сок,  сахарный колер Е 150d, консерванты (сорбат калия, бензоат  натрия)',
          },
          microelements: [
            {
              element: 'E,P',
            },
            {
              element: 'B,C',
            },
          ],
          energyValue: '9 ккал/ 37,8 кДж',
          image: 'garnet_3',
          fruitImage: 'garnet',
          slideMiniature: 'garnet',
        },
        // яблоко
        {
          id: 11,
          type: 'juice',
          volume: '0,5',
          tooltip: 'Яблоко',
          name: '0.5 л НАПИТОК безалкогольный НЕГАЗИРОВАННЫЙ ОСВЕТЛЕННЫЙ СО ВКУСОМ ЯБЛОКА',
          description: ``,
          benefit: 'Калий, входящий в состав напитка, помогает укрепить сердце и укрепляет сосуды.',
          macronutrients: [
            {
              name: 'Калории',
              value: '9 ккал/ 37,8 кДж.',
            },
            {
              name: 'Углеводы',
              value: '– 2 (± 0,2) г',
            },
          ],
          composition: {
            main: 'вода питьевая, сахарный сироп, сок яблочный, регулятор кислотности лимонная кислота, ароматизатор пищевой «Яблоко», подсластитель «Мультисвит 200F», краситель сахарный колер Е 150d, консерванты (сорбат калия, бензоат  натрия)',
          },
          microelements: [
            {
              element: 'А,С',
            },
            {
              element: 'К,В',
            },
          ],
          energyValue: '9 ккал/ 37,8 кДж',
          image: 'apple_05',
          fruitImage: 'apple',
          slideMiniature: 'apple',
        },
        {
          id: 12,
          type: 'juice',
          volume: '1',
          tooltip: 'Яблоко',
          name: '1 л НАПИТОК безалкогольный НЕГАЗИРОВАННЫЙ ОСВЕТЛЕННЫЙ СО ВКУСОМ ЯБЛОКА',
          description: ``,
          benefit: 'Калий, входящий в состав напитка, помогает укрепить сердце и укрепляет сосуды.',
          macronutrients: [
            {
              name: 'Калории',
              value: '9 ккал/ 37,8 кДж.',
            },
            {
              name: 'Углеводы',
              value: '– 2 (± 0,2) г',
            },
          ],
          composition: {
            main: 'вода питьевая, сахарный сироп, сок яблочный, регулятор кислотности лимонная кислота, ароматизатор пищевой «Яблоко», подсластитель «Мультисвит 200F», краситель сахарный колер Е 150d, консерванты (сорбат калия, бензоат  натрия)',
          },
          microelements: [
            {
              element: 'А,С',
            },
            {
              element: 'К,В',
            },
          ],
          energyValue: '9 ккал/ 37,8 кДж',
          image: 'apple_1',
          fruitImage: 'apple',
          slideMiniature: 'apple',
        },
        {
          id: 13,
          type: 'juice',
          volume: '3',
          tooltip: 'Яблоко',
          name: '3 л НАПИТОК безалкогольный НЕГАЗИРОВАННЫЙ ОСВЕТЛЕННЫЙ СО ВКУСОМ ЯБЛОКА',
          description: ``,
          benefit: 'Калий, входящий в состав напитка, помогает укрепить сердце и укрепляет сосуды.',
          macronutrients: [
            {
              name: 'Калории',
              value: '9 ккал/ 37,8 кДж.',
            },
            {
              name: 'Углеводы',
              value: '– 2 (± 0,2) г',
            },
          ],
          composition: {
            main: 'вода питьевая, сахарный сироп, сок яблочный, регулятор кислотности лимонная кислота, ароматизатор пищевой «Яблоко», подсластитель «Мультисвит 200F», краситель сахарный колер Е 150d, консерванты (сорбат калия, бензоат  натрия)',
          },
          microelements: [
            {
              element: 'А,С',
            },
            {
              element: 'К,В',
            },
          ],
          energyValue: '9 ккал/ 37,8 кДж',
          image: 'apple_3',
          fruitImage: 'apple',
          slideMiniature: 'apple',
        },
        {
          id: 14,
          type: 'juice',
          volume: '5',
          tooltip: 'Яблоко',
          name: '5 л НАПИТОК безалкогольный НЕГАЗИРОВАННЫЙ ОСВЕТЛЕННЫЙ СО ВКУСОМ ЯБЛОКА',
          description: ``,
          benefit: 'Калий, входящий в состав напитка, помогает укрепить сердце и укрепляет сосуды.',
          macronutrients: [
            {
              name: 'Калории',
              value: '9 ккал/ 37,8 кДж.',
            },
            {
              name: 'Углеводы',
              value: '– 2 (± 0,2) г',
            },
          ],
          composition: {
            main: 'вода питьевая, сахарный сироп, сок яблочный, регулятор кислотности лимонная кислота, ароматизатор пищевой «Яблоко», подсластитель «Мультисвит 200F», краситель сахарный колер Е 150d, консерванты (сорбат калия, бензоат  натрия)',
          },
          microelements: [
            {
              element: 'А,С',
            },
            {
              element: 'К,В',
            },
          ],
          energyValue: '9 ккал/ 37,8 кДж',
          image: 'apple_5',
          fruitImage: 'apple',
          slideMiniature: 'apple',
        },
        // вишня
        {
          id: 15,
          type: 'juice',
          volume: '0,5',
          tooltip: 'Вишня',
          name: '0.5 л НАПИТОК безалкогольный НЕГАЗИРОВАННЫЙ ОСВЕТЛЕННЫЙ СО ВКУСОМ ВИШНИ',
          description: ``,
          benefit: 'Калий, входящий в состав напитка, помогает укрепить сердце и укрепляет сосуды.',
          macronutrients: [
            {
              name: 'Калории',
              value: '9 ккал/ 37,8 кДж.',
            },
            {
              name: 'Углеводы',
              value: '– 2 (± 0,2) г',
            },
          ],
          composition: {
            main: 'вода питьевая, сахарный сироп, сок яблочный, регулятор кислотности лимонная кислота, ароматизатор пищевой «Вишня», подсластитель «Мультисвит 200F», краситель  сахарный колер Е 150d, консерванты (сорбат калия, бензоат  натрия)',
          },
          microelements: [
            {
              element: 'А,С',
            },
            {
              element: 'К,В',
            },
          ],
          energyValue: '9 ккал/ 37,8 кДж',
          image: 'cherry_05',
          fruitImage: 'cherry',
          slideMiniature: 'cherries',
        },
        {
          id: 16,
          type: 'juice',
          volume: '1',
          tooltip: 'Вишня',
          name: '1 л НАПИТОК безалкогольный НЕГАЗИРОВАННЫЙ ОСВЕТЛЕННЫЙ СО ВКУСОМ ВИШНИ',
          description: ``,
          benefit: 'Калий, входящий в состав напитка, помогает укрепить сердце и укрепляет сосуды.',
          macronutrients: [
            {
              name: 'Калории',
              value: '9 ккал/ 37,8 кДж.',
            },
            {
              name: 'Углеводы',
              value: '– 2 (± 0,2) г',
            },
          ],
          composition: {
            main: 'вода питьевая, сахарный сироп, сок яблочный, регулятор кислотности лимонная кислота, ароматизатор пищевой «Вишня», подсластитель «Мультисвит 200F», краситель  сахарный колер Е 150d, консерванты (сорбат калия, бензоат  натрия)',
          },
          microelements: [
            {
              element: 'А,С',
            },
            {
              element: 'К,В',
            },
          ],
          energyValue: '9 ккал/ 37,8 кДж',
          image: 'cherry_1',
          fruitImage: 'cherry',
          slideMiniature: 'cherries',
        },
        {
          id: 17,
          type: 'juice',
          volume: '3',
          tooltip: 'Вишня',
          name: '3 л НАПИТОК безалкогольный НЕГАЗИРОВАННЫЙ ОСВЕТЛЕННЫЙ СО ВКУСОМ ВИШНИ',
          description: ``,
          benefit: 'Калий, входящий в состав напитка, помогает укрепить сердце и укрепляет сосуды.',
          macronutrients: [
            {
              name: 'Калории',
              value: '9 ккал/ 37,8 кДж.',
            },
            {
              name: 'Углеводы',
              value: '– 2 (± 0,2) г',
            },
          ],
          composition: {
            main: 'вода питьевая, сахарный сироп, сок яблочный, регулятор кислотности лимонная кислота, ароматизатор пищевой «Вишня», подсластитель «Мультисвит 200F», краситель  сахарный колер Е 150d, консерванты (сорбат калия, бензоат  натрия)',
          },
          microelements: [
            {
              element: 'А,С',
            },
            {
              element: 'К,В',
            },
          ],
          energyValue: '9 ккал/ 37,8 кДж',
          image: 'cherry_3',
          fruitImage: 'cherry',
          slideMiniature: 'cherries',
        },
        {
          id: 18,
          type: 'juice',
          volume: '5',
          tooltip: 'Вишня',
          name: '5 л НАПИТОК безалкогольный НЕГАЗИРОВАННЫЙ ОСВЕТЛЕННЫЙ СО ВКУСОМ ВИШНИ',
          description: ``,
          benefit: 'Калий, входящий в состав напитка, помогает укрепить сердце и укрепляет сосуды.',
          macronutrients: [
            {
              name: 'Калории',
              value: '9 ккал/ 37,8 кДж.',
            },
            {
              name: 'Углеводы',
              value: '– 2 (± 0,2) г',
            },
          ],
          composition: {
            main: 'вода питьевая, сахарный сироп, сок яблочный, регулятор кислотности лимонная кислота, ароматизатор пищевой «Вишня», подсластитель «Мультисвит 200F», краситель  сахарный колер Е 150d, консерванты (сорбат калия, бензоат  натрия)',
          },
          microelements: [
            {
              element: 'А,С',
            },
            {
              element: 'К,В',
            },
          ],
          energyValue: '9 ккал/ 37,8 кДж',
          image: 'cherry_5',
          fruitImage: 'cherry',
          slideMiniature: 'cherries',
        },
        // мультифрукт
        {
          id: 19,
          type: 'juice',
          volume: '0,5',
          tooltip: 'Мультифрукт',
          name: '0.5 л НАПИТОК безалкогольный НЕГАЗИРОВАННЫЙ неосветленный СО ВКУСОМ ФРУКТОВ',
          description: ``,
          benefit: 'Калий, входящий в состав напитка, помогает укрепить сердце и укрепляет сосуды.',
          macronutrients: [
            {
              name: 'Калории',
              value: '9 ккал/ 37,8 кДж.',
            },
            {
              name: 'Углеводы',
              value: '– 2 (± 0,2) г',
            },
          ],
          composition: {
            main: 'вода питьевая, сахарный сироп, сок яблочный, регулятор кислотности лимонная кислота, ароматизатор пищевой «Тропик», подсластитель «Мультисвит 200F», аскорбиновая кислота, консерванты (сорбат калия, бензоат  натрия)',
          },
          microelements: [
            {
              element: 'А,С',
            },
            {
              element: 'К,В',
            },
            {
              element: 'β- каротин',
            },
          ],
          energyValue: '9 ккал/ 37,8 кДж',
          image: 'multifruct_05',
          fruitImage: 'multifruct',
          slideMiniature: 'multifruct',
        },
        {
          id: 20,
          type: 'juice',
          volume: '1',
          tooltip: 'Мультифрукт',
          name: '1 л НАПИТОК безалкогольный НЕГАЗИРОВАННЫЙ неосветленный СО ВКУСОМ ФРУКТОВ',
          description: ``,
          benefit: 'Калий, входящий в состав напитка, помогает укрепить сердце и укрепляет сосуды.',
          macronutrients: [
            {
              name: 'Калории',
              value: '9 ккал/ 37,8 кДж.',
            },
            {
              name: 'Углеводы',
              value: '– 2 (± 0,2) г',
            },
          ],
          composition: {
            main: 'вода питьевая, сахарный сироп, сок яблочный, регулятор кислотности лимонная кислота, ароматизатор пищевой «Тропик», подсластитель «Мультисвит 200F», аскорбиновая кислота, консерванты (сорбат калия, бензоат  натрия)',
          },
          microelements: [
            {
              element: 'А,С',
            },
            {
              element: 'К,В',
            },
            {
              element: 'β- каротин',
            },
          ],
          energyValue: '9 ккал/ 37,8 кДж',
          image: 'multifruct_1',
          fruitImage: 'multifruct',
          slideMiniature: 'multifruct',
        },
        {
          id: 21,
          type: 'juice',
          volume: '3',
          tooltip: 'Мультифрукт',
          name: '3 л НАПИТОК безалкогольный НЕГАЗИРОВАННЫЙ неосветленный СО ВКУСОМ ФРУКТОВ',
          description: ``,
          benefit: 'Калий, входящий в состав напитка, помогает укрепить сердце и укрепляет сосуды.',
          macronutrients: [
            {
              name: 'Калории',
              value: '9 ккал/ 37,8 кДж.',
            },
            {
              name: 'Углеводы',
              value: '– 2 (± 0,2) г',
            },
          ],
          composition: {
            main: 'вода питьевая, сахарный сироп, сок яблочный, регулятор кислотности лимонная кислота, ароматизатор пищевой «Тропик», подсластитель «Мультисвит 200F», аскорбиновая кислота, консерванты (сорбат калия, бензоат  натрия)',
          },
          microelements: [
            {
              element: 'А,С',
            },
            {
              element: 'К,В',
            },
            {
              element: 'β- каротин',
            },
          ],
          energyValue: '9 ккал/ 37,8 кДж',
          image: 'multifruct_3',
          fruitImage: 'multifruct',
          slideMiniature: 'multifruct',
        },
        {
          id: 22,
          type: 'juice',
          volume: '5',
          tooltip: 'Мультифрукт',
          name: '5 л НАПИТОК безалкогольный НЕГАЗИРОВАННЫЙ неосветленный СО ВКУСОМ ФРУКТОВ',
          description: ``,
          benefit: 'Калий, входящий в состав напитка, помогает укрепить сердце и укрепляет сосуды.',
          macronutrients: [
            {
              name: 'Калории',
              value: '9 ккал/ 37,8 кДж.',
            },
            {
              name: 'Углеводы',
              value: '– 2 (± 0,2) г',
            },
          ],
          composition: {
            main: 'вода питьевая, сахарный сироп, сок яблочный, регулятор кислотности лимонная кислота, ароматизатор пищевой «Тропик», подсластитель «Мультисвит 200F», аскорбиновая кислота, консерванты (сорбат калия, бензоат  натрия)',
          },
          microelements: [
            {
              element: 'А,С',
            },
            {
              element: 'К,В',
            },
            {
              element: 'β- каротин',
            },
          ],
          energyValue: '9 ккал/ 37,8 кДж',
          image: 'multifruct_5',
          fruitImage: 'multifruct',
          slideMiniature: 'multifruct',
        },
        // яблоко-клубника
        {
          id: 23,
          type: 'juice',
          volume: '3',
          tooltip: 'Яблоко-клубника',
          name: '3 л НАПИТОК безалкогольный НЕГАЗИРОВАННЫЙ ОСВЕТЛЕННЫЙ СО ВКУСОМ ЯБЛОКА-КЛУБНИКИ',
          description: ``,
          benefit: 'Калий, входящий в состав напитка, помогает укрепить сердце и укрепляет сосуды.',
          macronutrients: [
            {
              name: 'Калории',
              value: '9 ккал/ 37,8 кДж.',
            },
            {
              name: 'Углеводы',
              value: '– 2 (± 0,2) г',
            },
          ],
          composition: {
            main: 'вода питьевая, сахарный сироп, сок яблочный, регулятор кислотности лимонная кислота, ароматизатор пищевой «яблоко - клубника», подсластитель «Мультисвит 200F», аскорбиновая кислота, консерванты (сорбат калия, бензоат  натрия)',
          },
          microelements: [
            {
              element: 'А,С',
            },
            {
              element: 'К,В',
            },
          ],
          energyValue: '9 ккал/ 37,8 кДж',
          image: 'apple_strawberry_3',
          fruitImage: 'strawberry',
          slideMiniature: 'apple_strawberry',
        },
        {
          id: 24,
          type: 'juice',
          volume: '5',
          tooltip: 'Яблоко-клубника',
          name: '5 л НАПИТОК безалкогольный НЕГАЗИРОВАННЫЙ ОСВЕТЛЕННЫЙ СО ВКУСОМ ЯБЛОКА-КЛУБНИКИ',
          description: ``,
          benefit: 'Калий, входящий в состав напитка, помогает укрепить сердце и укрепляет сосуды.',
          macronutrients: [
            {
              name: 'Калории',
              value: '9 ккал/ 37,8 кДж.',
            },
            {
              name: 'Углеводы',
              value: '– 2 (± 0,2) г',
            },
          ],
          composition: {
            main: 'вода питьевая, сахарный сироп, сок яблочный, регулятор кислотности лимонная кислота, ароматизатор пищевой «яблоко - клубника», подсластитель «Мультисвит 200F», аскорбиновая кислота, консерванты (сорбат калия, бензоат  натрия)',
          },
          microelements: [
            {
              element: 'А,С',
            },
            {
              element: 'К,В',
            },
          ],
          energyValue: '9 ккал/ 37,8 кДж',
          image: 'apple_strawberry_5',
          fruitImage: 'strawberry',
          slideMiniature: 'apple_strawberry',
        },
        // сиропы
        {
          id: 25,
          type: 'syrup',
          volume: '3',
          tooltip: 'Барбарис',
          name: '3 л СИРОП «БАРБАРИС»',
          description: `Рекомендации по использованию: сироп добавляют по вкусу в кофе, коктейли, мороженное, десерты, либо разбавлять водой с соотношении 1 : 5.`,
          benefit: 'Калий, входящий в состав напитка, помогает укрепить сердце и укрепляет сосуды.',
          macronutrients: [
            {
              name: 'Калории',
              value: '220 ккал/ 920 кДж.',
            },
            {
              name: 'Углеводы',
              value: '55 г',
            },
          ],
          composition:
            'Сиропы представляют собой вязкие, однородные по консистенции, сладкие продукты с различными вкусами',
          microelements: [
            {
              element: 'А,С',
            },
            {
              element: 'К,В',
            },
            {
              element: 'β- каротин',
            },
          ],
          energyValue: '220 ккал/ 920 кДж',
          image: 'syrup_barberry_3',
          fruitImage: 'barberry',
          slideMiniature: 'barberry',
        },
        {
          id: 26,
          type: 'syrup',
          volume: '3',
          tooltip: 'Лимон',
          name: '3 л СИРОП «ЛИМОН»',
          description: `Рекомендации по использованию: сироп добавляют по вкусу в кофе, коктейли, мороженное, десерты, либо разбавлять водой с соотношении 1 : 5.`,
          benefit: 'Калий, входящий в состав напитка, помогает укрепить сердце и укрепляет сосуды.',
          macronutrients: [
            {
              name: 'Калории',
              value: '220 ккал/ 920 кДж.',
            },
            {
              name: 'Углеводы',
              value: '55 г',
            },
          ],
          composition:
            'Сиропы представляют собой вязкие, однородные по консистенции, сладкие продукты с различными вкусами',
          microelements: [
            {
              element: 'А,С',
            },
            {
              element: 'К,В',
            },
            {
              element: 'β- каротин',
            },
          ],
          energyValue: '220 ккал/ 920 кДж',
          image: 'syrup_lemon_3',
          fruitImage: 'lemon',
          slideMiniature: 'lemon',
        },
        {
          id: 27,
          type: 'syrup',
          volume: '3',
          tooltip: 'Апельсин',
          name: '3 л СИРОП «АПЕЛЬСИН»',
          description: `Рекомендации по использованию: сироп добавляют по вкусу в кофе, коктейли, мороженное, десерты, либо разбавлять водой с соотношении 1 : 5.`,
          benefit: 'Калий, входящий в состав напитка, помогает укрепить сердце и укрепляет сосуды.',
          macronutrients: [
            {
              name: 'Калории',
              value: '220 ккал/ 920 кДж.',
            },
            {
              name: 'Углеводы',
              value: '55 г',
            },
          ],
          composition:
            'Сиропы представляют собой вязкие, однородные по консистенции, сладкие продукты с различными вкусами',
          microelements: [
            {
              element: 'А,С',
            },
            {
              element: 'К,В',
            },
            {
              element: 'β- каротин',
            },
          ],
          energyValue: '220 ккал/ 920 кДж',
          image: 'syrup_orange_3',
          fruitImage: 'orange',
          slideMiniature: 'orange',
        },
        {
          id: 28,
          type: 'syrup',
          volume: '3',
          tooltip: 'Дюшес',
          name: '3 л СИРОП «ДЮШЕС»',
          description: `Рекомендации по использованию: сироп добавляют по вкусу в кофе, коктейли, мороженное, десерты, либо разбавлять водой с соотношении 1 : 5.`,
          benefit: 'Калий, входящий в состав напитка, помогает укрепить сердце и укрепляет сосуды.',
          macronutrients: [
            {
              name: 'Калории',
              value: '220 ккал/ 920 кДж.',
            },
            {
              name: 'Углеводы',
              value: '55 г',
            },
          ],
          composition:
            'Сиропы представляют собой вязкие, однородные по консистенции, сладкие продукты с различными вкусами',
          microelements: [
            {
              element: 'А,С',
            },
            {
              element: 'К,В',
            },
            {
              element: 'β- каротин',
            },
          ],
          energyValue: '220 ккал/ 920 кДж',
          image: 'syrup_pear_3',
          fruitImage: 'pear',
          slideMiniature: 'duchesse_pear',
        },
        {
          id: 29,
          type: 'syrup',
          volume: '3',
          tooltip: 'Малина',
          name: '3 л СИРОП «МАЛИНА»',
          description: `Рекомендации по использованию: сироп добавляют по вкусу в кофе, коктейли, мороженное, десерты, либо разбавлять водой с соотношении 1 : 5.`,
          benefit: 'Калий, входящий в состав напитка, помогает укрепить сердце и укрепляет сосуды.',
          macronutrients: [
            {
              name: 'Калории',
              value: '220 ккал/ 920 кДж.',
            },
            {
              name: 'Углеводы',
              value: '55 г',
            },
          ],
          composition:
            'Сиропы представляют собой вязкие, однородные по консистенции, сладкие продукты с различными вкусами',
          microelements: [
            {
              element: 'А,С',
            },
            {
              element: 'К,В',
            },
            {
              element: 'β- каротин',
            },
          ],
          energyValue: '220 ккал/ 920 кДж',
          image: 'syrup_raspberries_3',
          fruitImage: 'raspberries',
          slideMiniature: 'raspberries',
        },
        {
          id: 30,
          type: 'syrup',
          volume: '3',
          tooltip: 'Клубника',
          name: '3 л СИРОП «КЛУБНИКА»',
          description: `Рекомендации по использованию: сироп добавляют по вкусу в кофе, коктейли, мороженное, десерты, либо разбавлять водой с соотношении 1 : 5.`,
          benefit: 'Калий, входящий в состав напитка, помогает укрепить сердце и укрепляет сосуды.',
          macronutrients: [
            {
              name: 'Калории',
              value: '220 ккал/ 920 кДж.',
            },
            {
              name: 'Углеводы',
              value: '55 г',
            },
          ],
          composition:
            'Сиропы представляют собой вязкие, однородные по консистенции, сладкие продукты с различными вкусами',
          microelements: [
            {
              element: 'А,С',
            },
            {
              element: 'К,В',
            },
            {
              element: 'β- каротин',
            },
          ],
          energyValue: '220 ккал/ 920 кДж',
          image: 'syrup_strawberry_3',
          fruitImage: 'strawberry',
          slideMiniature: 'strawberry',
        },
        {
          id: 31,
          type: 'syrup',
          volume: '3',
          tooltip: 'Тархун',
          name: '3 л СИРОП «ТАРХУН»',
          description: `Рекомендации по использованию: сироп добавляют по вкусу в кофе, коктейли, мороженное, десерты, либо разбавлять водой с соотношении 1 : 5.`,
          benefit: 'Калий, входящий в состав напитка, помогает укрепить сердце и укрепляет сосуды.',
          macronutrients: [
            {
              name: 'Калории',
              value: '220 ккал/ 920 кДж.',
            },
            {
              name: 'Углеводы',
              value: '55 г',
            },
          ],
          composition:
            'Сиропы представляют собой вязкие, однородные по консистенции, сладкие продукты с различными вкусами',
          microelements: [
            {
              element: 'А,С',
            },
            {
              element: 'К,В',
            },
            {
              element: 'β- каротин',
            },
          ],
          energyValue: '220 ккал/ 920 кДж',
          image: 'syrup_tarragon_3',
          fruitImage: 'tarragon',
          slideMiniature: 'tarragon',
        },
        // узвары
        {
          id: 32,
          type: 'uzvar',
          volume: '0,5',
          tooltip: 'Ассорти',
          name: '0.5 л УЗВАР «АССОРТИ» НАПИТОК ИЗ СУХОФРУКТОВ',
          description: `Приготовлен из сушенных плодов груши, яблока, шиповника, чернослива, абрикоса путем варки и последующего процеживания. При производстве используются натуральные продукты.`,
          benefit: 'Калий, входящий в состав напитка, помогает укрепить сердце и укрепляет сосуды.',
          macronutrients: [
            {
              name: 'Калории',
              value: '18 ккал/ 75,6 кДж.',
            },
            {
              name: 'Углеводы',
              value: '– 4,3 (± 0,2) г',
            },
          ],
          composition: {
            main: 'настой сушенных плодов груши, яблока, шиповника, чернослива, абрикоса, сахарный сироп, регулятор кислотности лимонная кислота, подсластитель «Мультисвит 200F», краситель сахарный колер Е 150d, консерванты (сорбат калия, бензоат  натрия)',
            additional:
              'Содержит подсластитель. При чрезмерном употреблении может оказывать слабительное действие',
          },
          microelements: [
            {
              element: 'А,С',
            },
            {
              element: 'К,В',
            },
          ],
          energyValue: '18 ккал/ 75,6 кДж',
          image: 'uzvar_assorted_05',
          fruitImage: 'assorted',
          slideMiniature: 'assorted',
        },
        {
          id: 33,
          type: 'uzvar',
          volume: '1',
          tooltip: 'Ассорти',
          name: '1 л УЗВАР «АССОРТИ» НАПИТОК ИЗ СУХОФРУКТОВ',
          description: `Приготовлен из сушенных плодов груши, яблока, шиповника, чернослива, абрикоса путем варки и последующего процеживания. При производстве используются натуральные продукты.`,
          benefit: 'Калий, входящий в состав напитка, помогает укрепить сердце и укрепляет сосуды.',
          macronutrients: [
            {
              name: 'Калории',
              value: '18 ккал/ 75,6 кДж.',
            },
            {
              name: 'Углеводы',
              value: '– 4,3 (± 0,2) г',
            },
          ],
          composition: {
            main: 'настой сушенных плодов груши, яблока, шиповника, чернослива, абрикоса, сахарный сироп, регулятор кислотности лимонная кислота, подсластитель «Мультисвит 200F», краситель сахарный колер Е 150d, консерванты (сорбат калия, бензоат  натрия)',
            additional:
              'Содержит подсластитель. При чрезмерном употреблении может оказывать слабительное действие',
          },
          microelements: [
            {
              element: 'А,С',
            },
            {
              element: 'К,В',
            },
          ],
          energyValue: '18 ккал/ 75,6 кДж',
          image: 'uzvar_assorted_1',
          fruitImage: 'assorted',
          slideMiniature: 'assorted',
        },
        {
          id: 34,
          type: 'uzvar',
          volume: '3',
          tooltip: 'Ассорти',
          name: '3 л УЗВАР «АССОРТИ» НАПИТОК ИЗ СУХОФРУКТОВ',
          description: `Приготовлен из сушенных плодов груши, яблока, шиповника, чернослива, абрикоса путем варки и последующего процеживания. При производстве используются натуральные продукты.`,
          benefit: 'Калий, входящий в состав напитка, помогает укрепить сердце и укрепляет сосуды.',
          macronutrients: [
            {
              name: 'Калории',
              value: '18 ккал/ 75,6 кДж.',
            },
            {
              name: 'Углеводы',
              value: '– 4,3 (± 0,2) г',
            },
          ],
          composition: {
            main: 'настой сушенных плодов груши, яблока, шиповника, чернослива, абрикоса, сахарный сироп, регулятор кислотности лимонная кислота, подсластитель «Мультисвит 200F», краситель сахарный колер Е 150d, консерванты (сорбат калия, бензоат  натрия)',
            additional:
              'Содержит подсластитель. При чрезмерном употреблении может оказывать слабительное действие',
          },
          microelements: [
            {
              element: 'А,С',
            },
            {
              element: 'К,В',
            },
          ],
          energyValue: '18 ккал/ 75,6 кДж',
          image: 'uzvar_assorted_3',
          fruitImage: 'assorted',
          slideMiniature: 'assorted',
        },
        {
          id: 35,
          type: 'uzvar',
          volume: '5',
          tooltip: 'Ассорти',
          name: '5 л УЗВАР «АССОРТИ» НАПИТОК ИЗ СУХОФРУКТОВ',
          description: `Приготовлен из сушенных плодов груши, яблока, шиповника, чернослива, абрикоса путем варки и последующего процеживания. При производстве используются натуральные продукты.`,
          benefit: 'Калий, входящий в состав напитка, помогает укрепить сердце и укрепляет сосуды.',
          macronutrients: [
            {
              name: 'Калории',
              value: '18 ккал/ 75,6 кДж.',
            },
            {
              name: 'Углеводы',
              value: '– 4,3 (± 0,2) г',
            },
          ],
          composition: {
            main: 'настой сушенных плодов груши, яблока, шиповника, чернослива, абрикоса, сахарный сироп, регулятор кислотности лимонная кислота, подсластитель «Мультисвит 200F», краситель сахарный колер Е 150d, консерванты (сорбат калия, бензоат  натрия)',
            additional:
              'Содержит подсластитель. При чрезмерном употреблении может оказывать слабительное действие',
          },
          microelements: [
            {
              element: 'А,С',
            },
            {
              element: 'К,В',
            },
          ],
          energyValue: '18 ккал/ 75,6 кДж',
          image: 'uzvar_assorted_5',
          fruitImage: 'assorted',
          slideMiniature: 'assorted',
        },
        {
          id: 36,
          type: 'uzvar',
          volume: '0,5',
          tooltip: 'Груша-дичка',
          name: '0.5 л УЗВАР «ГРУША - ДИЧКА» НАПИТОК ИЗ СУХОФРУКТОВ',
          description: `Приготовлен из сушенных плодов груши – дички путем варки и последующего процеживания. При производстве используются натуральные продукты.`,
          benefit: 'Калий, входящий в состав напитка, помогает укрепить сердце и укрепляет сосуды.',
          macronutrients: [
            {
              name: 'Калории',
              value: '18 ккал/ 75,6 кДж.',
            },
            {
              name: 'Углеводы',
              value: '– 4,3 (± 0,2) г',
            },
          ],
          composition: {
            main: 'настой сушенных плодов груши - дички, сахарный сироп, регулятор кислотности лимонная кислота, подсластитель «Мультисвит 200F», краситель сахарный колер Е 150d, консерванты (сорбат калия, бензоат  натрия)',
            additional:
              'Содержит подсластитель. При чрезмерном употреблении может оказывать слабительное действие',
          },
          microelements: [
            {
              element: 'А,С',
            },
            {
              element: 'К,В',
            },
          ],
          energyValue: '18 ккал/ 75,6 кДж',
          image: 'uzvar_pear_05',
          fruitImage: 'pear',
          slideMiniature: 'wild_pear',
        },
        {
          id: 37,
          type: 'uzvar',
          volume: '1',
          tooltip: 'Груша-дичка',
          name: '1 л УЗВАР «ГРУША - ДИЧКА» НАПИТОК ИЗ СУХОФРУКТОВ',
          description: `Приготовлен из сушенных плодов груши – дички путем варки и последующего процеживания. При производстве используются натуральные продукты.`,
          benefit: 'Калий, входящий в состав напитка, помогает укрепить сердце и укрепляет сосуды.',
          macronutrients: [
            {
              name: 'Калории',
              value: '18 ккал/ 75,6 кДж.',
            },
            {
              name: 'Углеводы',
              value: '– 4,3 (± 0,2) г',
            },
          ],
          composition: {
            main: 'настой сушенных плодов груши - дички, сахарный сироп, регулятор кислотности лимонная кислота, подсластитель «Мультисвит 200F», краситель сахарный колер Е 150d, консерванты (сорбат калия, бензоат  натрия)',
            additional:
              'Содержит подсластитель. При чрезмерном употреблении может оказывать слабительное действие',
          },
          microelements: [
            {
              element: 'А,С',
            },
            {
              element: 'К,В',
            },
          ],
          energyValue: '18 ккал/ 75,6 кДж',
          image: 'uzvar_pear_1',
          fruitImage: 'pear',
          slideMiniature: 'wild_pear',
        },
        {
          id: 38,
          type: 'uzvar',
          volume: '3',
          tooltip: 'Груша-дичка',
          name: '3 л УЗВАР «ГРУША - ДИЧКА» НАПИТОК ИЗ СУХОФРУКТОВ',
          description: `Приготовлен из сушенных плодов груши – дички путем варки и последующего процеживания. При производстве используются натуральные продукты.`,
          benefit: 'Калий, входящий в состав напитка, помогает укрепить сердце и укрепляет сосуды.',
          macronutrients: [
            {
              name: 'Калории',
              value: '18 ккал/ 75,6 кДж.',
            },
            {
              name: 'Углеводы',
              value: '– 4,3 (± 0,2) г',
            },
          ],
          composition: {
            main: 'настой сушенных плодов груши - дички, сахарный сироп, регулятор кислотности лимонная кислота, подсластитель «Мультисвит 200F», краситель сахарный колер Е 150d, консерванты (сорбат калия, бензоат  натрия)',
            additional:
              'Содержит подсластитель. При чрезмерном употреблении может оказывать слабительное действие',
          },
          microelements: [
            {
              element: 'А,С',
            },
            {
              element: 'К,В',
            },
          ],
          energyValue: '18 ккал/ 75,6 кДж',
          image: 'uzvar_pear_3',
          fruitImage: 'pear',
          slideMiniature: 'wild_pear',
        },
        {
          id: 39,
          type: 'uzvar',
          volume: '5',
          tooltip: 'Груша-дичка',
          name: '5 л УЗВАР «ГРУША - ДИЧКА» НАПИТОК ИЗ СУХОФРУКТОВ',
          description: `Приготовлен из сушенных плодов груши – дички путем варки и последующего процеживания. При производстве используются натуральные продукты.`,
          benefit: 'Калий, входящий в состав напитка, помогает укрепить сердце и укрепляет сосуды.',
          macronutrients: [
            {
              name: 'Калории',
              value: '18 ккал/ 75,6 кДж.',
            },
            {
              name: 'Углеводы',
              value: '– 4,3 (± 0,2) г',
            },
          ],
          composition: {
            main: 'настой сушенных плодов груши - дички, сахарный сироп, регулятор кислотности лимонная кислота, подсластитель «Мультисвит 200F», краситель сахарный колер Е 150d, консерванты (сорбат калия, бензоат  натрия)',
            additional:
              'Содержит подсластитель. При чрезмерном употреблении может оказывать слабительное действие',
          },
          microelements: [
            {
              element: 'А,С',
            },
            {
              element: 'К,В',
            },
          ],
          energyValue: '18 ккал/ 75,6 кДж',
          image: 'uzvar_pear_5',
          fruitImage: 'pear',
          slideMiniature: 'wild_pear',
        },
        // мохито
        {
          id: 40,
          type: 'juice',
          volume: '0,5',
          tooltip: 'Мохито',
          name: '0.5 л НАПИТОК безалкогольный НЕГАЗИРОВАННЫЙ НЕОСВЕТЛЕННЫЙ МОХИТО',
          description: ``,
          benefit: 'Калий, входящий в состав напитка, помогает укрепить сердце и укрепляет сосуды.',
          macronutrients: [
            {
              name: 'Калории',
              value: '9 ккал/ 37,8 кДж.',
            },
            {
              name: 'Углеводы',
              value: '– 2 (± 0,2) г',
            },
          ],
          composition: {
            main: 'вода питьевая, сахарный сироп, регулятор кислотности лимонная кислота, ароматизатор пищевой «лайм - мята», ароматизатор пищевой «лимон – лайм»,  ароматизатор пищевой «замутнитель», подсластитель «мультисвит 200F», консерванты (сорбат калия, бензоат  натрия)',
          },
          microelements: [
            {
              element: 'А,С',
            },
            {
              element: 'К,В',
            },
          ],
          energyValue: '9 ккал/ 37,8 кДж',
          image: 'no_name',
          fruitImage: 'no_name',
          slideMiniature: 'mojito',
        },
        {
          id: 41,
          type: 'juice',
          volume: '1',
          tooltip: 'Мохито',
          name: '1 л НАПИТОК безалкогольный НЕГАЗИРОВАННЫЙ НЕОСВЕТЛЕННЫЙ МОХИТО',
          description: ``,
          benefit: 'Калий, входящий в состав напитка, помогает укрепить сердце и укрепляет сосуды.',
          macronutrients: [
            {
              name: 'Калории',
              value: '9 ккал/ 37,8 кДж.',
            },
            {
              name: 'Углеводы',
              value: '– 2 (± 0,2) г',
            },
          ],
          composition: {
            main: 'вода питьевая, сахарный сироп, регулятор кислотности лимонная кислота, ароматизатор пищевой «лайм - мята», ароматизатор пищевой «лимон – лайм»,  ароматизатор пищевой «замутнитель», подсластитель «мультисвит 200F», консерванты (сорбат калия, бензоат  натрия)',
          },
          microelements: [
            {
              element: 'А,С',
            },
            {
              element: 'К,В',
            },
          ],
          energyValue: '9 ккал/ 37,8 кДж',
          image: 'no_name',
          fruitImage: 'no_name',
          slideMiniature: 'mojito',
        },
        {
          id: 42,
          type: 'juice',
          volume: '3',
          tooltip: 'Мохито',
          name: '3 л НАПИТОК безалкогольный НЕГАЗИРОВАННЫЙ НЕОСВЕТЛЕННЫЙ МОХИТО',
          description: ``,
          benefit: 'Калий, входящий в состав напитка, помогает укрепить сердце и укрепляет сосуды.',
          macronutrients: [
            {
              name: 'Калории',
              value: '9 ккал/ 37,8 кДж.',
            },
            {
              name: 'Углеводы',
              value: '– 2 (± 0,2) г',
            },
          ],
          composition: {
            main: 'вода питьевая, сахарный сироп, регулятор кислотности лимонная кислота, ароматизатор пищевой «лайм - мята», ароматизатор пищевой «лимон – лайм»,  ароматизатор пищевой «замутнитель», подсластитель «мультисвит 200F», консерванты (сорбат калия, бензоат  натрия)',
          },
          microelements: [
            {
              element: 'А,С',
            },
            {
              element: 'К,В',
            },
          ],
          energyValue: '9 ккал/ 37,8 кДж',
          image: 'no_name',
          fruitImage: 'no_name',
          slideMiniature: 'mojito',
        },
        {
          id: 43,
          type: 'juice',
          volume: '5',
          tooltip: 'Мохито',
          name: '5 л НАПИТОК безалкогольный НЕГАЗИРОВАННЫЙ НЕОСВЕТЛЕННЫЙ МОХИТО',
          description: ``,
          benefit: 'Калий, входящий в состав напитка, помогает укрепить сердце и укрепляет сосуды.',
          macronutrients: [
            {
              name: 'Калории',
              value: '9 ккал/ 37,8 кДж.',
            },
            {
              name: 'Углеводы',
              value: '– 2 (± 0,2) г',
            },
          ],
          composition: {
            main: 'вода питьевая, сахарный сироп, регулятор кислотности лимонная кислота, ароматизатор пищевой «лайм - мята», ароматизатор пищевой «лимон – лайм»,  ароматизатор пищевой «замутнитель», подсластитель «мультисвит 200F», консерванты (сорбат калия, бензоат  натрия)',
          },
          microelements: [
            {
              element: 'А,С',
            },
            {
              element: 'К,В',
            },
          ],
          energyValue: '9 ккал/ 37,8 кДж',
          image: 'no_name',
          fruitImage: 'no_name',
          slideMiniature: 'mojito',
        },
        // томат
        {
          id: 44,
          type: 'juice',
          volume: '0,5',
          tooltip: 'Томат',
          name: '0.5 л НАПИТОК безалкогольный НЕГАЗИРОВАННЫЙ НЕОСВЕТЛЕННЫЙ НА РАСТИТЕЛЬНОМ СЫРЬЕ «ТОМАТ»',
          description: `Сок “Прогулка по саду” “томат”  содержит природные пищевые волокна,
                        которые являются отличным средством нормализации работы желудочно-кишечного
                        тракта.`,
          benefit: 'Калий, входящий в состав напитка, помогает укрепить сердце и укрепляет сосуды.',
          macronutrients: [
            {
              name: 'Калории',
              value: '18 ккал/ 75,8 кДж.',
            },
            {
              name: 'Углеводы',
              value: '4 г',
            },
          ],
          composition: {
            main: 'вода питьевая, томатная паста, соль, грин аква гель, консерванты (сорбат калия, бензоат  натрия)',
          },
          microelements: [
            {
              element: 'А,С',
            },
            {
              element: 'К,В',
            },
            {
              element: 'P',
            },
          ],
          energyValue: '18 ккал/ 75,8 кДж.',
          image: 'no_name',
          fruitImage: 'no_name',
          slideMiniature: 'tomato',
        },
        {
          id: 45,
          type: 'juice',
          volume: '1',
          tooltip: 'Томат',
          name: '1 л НАПИТОК безалкогольный НЕГАЗИРОВАННЫЙ НЕОСВЕТЛЕННЫЙ НА РАСТИТЕЛЬНОМ СЫРЬЕ «ТОМАТ»',
          description: `Сок “Прогулка по саду” “томат”  содержит природные пищевые волокна,
                        которые являются отличным средством нормализации работы желудочно-кишечного
                        тракта.`,
          benefit: 'Калий, входящий в состав напитка, помогает укрепить сердце и укрепляет сосуды.',
          macronutrients: [
            {
              name: 'Калории',
              value: '18 ккал/ 75,8 кДж.',
            },
            {
              name: 'Углеводы',
              value: '4 г',
            },
          ],
          composition: {
            main: 'вода питьевая, томатная паста, соль, грин аква гель, консерванты (сорбат калия, бензоат  натрия)',
          },
          microelements: [
            {
              element: 'А,С',
            },
            {
              element: 'К,В',
            },
            {
              element: 'P',
            },
          ],
          energyValue: '18 ккал/ 75,8 кДж.',
          image: 'no_name',
          fruitImage: 'no_name',
          slideMiniature: 'tomato',
        },
      ],

      filterByVolume: {},
      filterByType: '',
      chosenJuice: {},
      currentJuiceMiniature: '',
      isVolumeFilterOpened: false,
      isTypeFilterOpened: false,

      swiperOption: {
        direction: 'horizontal',
        slidesPerView: 3,
        navigation: {
          nextEl: '.button-next',
          prevEl: '.button-prev',
        },
        breakpoints: {
          1200: {
            direction: 'vertical',
            slidesPerView: 5,
          },
          720: {
            slidesPerView: 5,
          },
        },
      },
    };
  },

  head: {
    title: 'Продукты',
  },

  computed: {
    sortingJuicesByVolume() {
      return this.juices.filter((juice) => juice.volume === this.filterByVolume.value);
    },
    sortingJuicesByType() {
      return this.sortingJuicesByVolume.filter((juice) => juice.type === this.filterByType.type);
    },
    swiper() {
      return this.$refs.swiper.$swiper;
    },
  },

  created() {
    if (!JSON.parse(localStorage.getItem('product'))) {
      this.filterByType = {
        name: typeFilters[0].name,
        type: typeFilters[0].type,
      };
      this.filterByVolume = {
        id: volumeFilters[0].id,
        value: volumeFilters[0].value,
      };
      this.chosenJuice = this.sortingJuicesByType[0];
      this.currentJuiceMiniature = this.chosenJuice;
    } else {
      const product = JSON.parse(localStorage.getItem('product'));

      this.filterByType = {
        name: product.name,
        type: product.type,
      };
      this.filterByVolume = {
        id: product.idForFilter,
        value: product.value,
      };
      this.chosenJuice = this.sortingJuicesByType[0];
      this.currentJuiceMiniature = this.chosenJuice;
    }
  },

  methods: {
    selectVolume(item) {
      this.filterByVolume = item;
      this.chosenJuice = this.sortingJuicesByType[0];
      this.currentJuiceMiniature = this.chosenJuice;
      this.isVolumeFilterOpened = false;

      if (this.filterByType.type === 'syrup') {
        this.filterByType = this.typeFilters[0];
        this.chosenJuice = this.sortingJuicesByType[0];
        this.currentJuiceMiniature = this.chosenJuice;
      }
      this.swiper.slideTo(0, 500, true);
    },
    selectType(item) {
      this.filterByType = item;
      this.chosenJuice = this.sortingJuicesByType[0];
      this.currentJuiceMiniature = this.chosenJuice;
      this.isTypeFilterOpened = false;
      this.swiper.slideTo(0, 500, true);
    },
    selectSyrupType() {
      this.filterByType = {
        id: 3,
        name: 'Сиропы',
        type: 'syrup',
      };
      this.chosenJuice = this.sortingJuicesByType[0];
      this.currentJuiceMiniature = this.chosenJuice;
      this.isTypeFilterOpened = false;
      this.swiper.slideTo(0, 500, true);
    },
    toggleVolumeFilter() {
      this.isVolumeFilterOpened = !this.isVolumeFilterOpened;
      this.isTypeFilterOpened = false;
    },
    chooseSlide(juice, index) {
      // this.swiper.slideTo(index, 500, false);
      this.chosenJuice = juice;
    },
  },
};
</script>

<style lang="scss">
$primaryFontColor: #4b4961;
.swiper {
  width: 315px;
  height: 676px;
  margin-top: 120px;
}
.slider__container {
  position: relative;
}
.main {
  font-family: Montserrat Alternates;
}
.filter {
  position: relative;

  height: 670px;

  overflow: hidden;
  margin-bottom: 50px;
  padding: 100px 100px 0;
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
  font-size: 64px;
  line-height: 87px;
  color: $primaryFontColor;
}

.filter__list {
  display: flex;
  flex-wrap: wrap;
  gap: 30px;

  margin-top: 53px;

  &_active {
    box-shadow: 0 4px 17px rgba(159, 159, 159, 0.2);
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
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 19px;

  width: 220px;
  height: 106px;

  background-color: #fff;
  border-radius: 6px;

  cursor: pointer;
  transition: 0.4s;

  &:hover {
    box-shadow: 0 4px 17px rgba(159, 159, 159, 0.2);

    path {
      stroke: url(#containerGradient);
    }
    transition: 0.2s;
  }
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

  &:hover {
    box-shadow: 0 4px 17px rgba(159, 159, 159, 0.2);
  }

  &_active {
    background: linear-gradient(269.21deg, #ffd25a 0.49%, #ffc52b 100%);
    span {
      color: #fff;
    }
  }

  &_hidden {
    display: none;
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

.slider {
  position: relative;
  display: flex;
  align-items: flex-start;

  margin-top: 20px;
  padding: 0 100px 160px;

  border-bottom: 1px solid #eaeaea;
  overflow-y: hidden;
}
.slider__container_mobile {
  display: none;
}
.slider__bottom-bg {
  width: 100%;
  position: absolute;
  bottom: -970px;
  left: 0;

  z-index: -1;
}
.slider__tooltip_mobile {
  display: none;
  background: #20b84f;
  border-radius: 6px;
  color: #fff;
  font-family: Rubik;
  white-space: nowrap;
  font-size: 18px;
  padding: 3px 18px;
  transition: all 0.6s;
  margin: 0 auto;
}

.juice-miniature_active {
  .juice-miniature {
    border: 2px solid #ffc52b;
    transform: translateX(30px);
    pointer-events: none;
  }
  .juice__tooltip {
    opacity: 1;
  }
}
.button-prev,
.button-next {
  position: absolute;
  z-index: 100;
  cursor: pointer;
}
.button-prev {
  top: 70px;
  left: 27px;
}
.button-next {
  bottom: 0;
  left: 25px;
}
.swiper-button-disabled {
  display: none;
}

.filter-dropdown {
  position: relative;
  display: none;
}
.filter-dropdown__toggle {
  width: 100%;
  display: flex;
  justify-content: space-between;

  background: linear-gradient(269.21deg, #ffd25a 0.49%, #ffc52b 100%);
  border: none;
  border-radius: 10px;

  padding: 12px 11px 10px 15px;

  font-weight: bold;
  font-size: 20px;
  line-height: 28px;
  color: #fff;
  text-align: center;

  transition-duration: 0.2s;
  transition-property: background-color, fill, color;

  outline: none;
  box-shadow: none;
  cursor: pointer;
  text-decoration: none;
}
.filter-dropdown__icon {
  transform: none;
  background: url('~@/assets/img/chevron-down.svg') no-repeat;
  background-size: contain;
  width: 30px;
  height: 30px;
  transition: 0.2s transform;
}
.filter-dropdown_opened .filter-dropdown__toggle {
  border-bottom-left-radius: 0;
  border-bottom-right-radius: 0;
}
.filter-dropdown_opened .filter-dropdown__toggle .filter-dropdown__icon {
  transform: rotate(180deg);
}
.filter-dropdown__menu {
  margin: 0;
  width: 100%;
  padding: 0;
  left: 0;
  z-index: 95;
  background-clip: padding-box;
  display: none;
  flex-direction: column;
  border: 2px solid var(--blue);
  border-top: none;
  overflow: hidden;
}
.filter-dropdown_opened .filter-dropdown__menu {
  display: flex;
  position: absolute;
  transform: translate3d(0px, 52px, 0px);
  top: -1px;
  left: 0;
  will-change: transform;
  right: auto;
  bottom: auto;
  transition: 0.5s ease;
}
.filter-dropdown__item {
  padding: 16px 12px;
  font-weight: 500;
  font-size: 20px;
  line-height: 28px;
  background-color: #fff;
  box-shadow: none;
  border-left: 1px solid #ffd25a;
  border-right: 1px solid #ffd25a;
  cursor: pointer;
  text-align: left;
  transition-duration: 0.2s;
  transition-property: background-color, border-color, color;
  outline: none;
  text-decoration: none;

  &:first-child {
    border-top: 1px solid #ffd25a;
  }
  &:last-child {
    border-bottom: 1px solid #ffd25a;
    border-radius: 0 0 10px 10px;
  }
  &:hover {
    background-color: #ffd25a;
  }
}

.filter-dropdown__toggle_second {
  background: #fff;
  border: 1px solid #ffd25a;
  color: #4b4961;
  font-weight: 500;
}
.filter-dropdown__icon_second {
  background: url('~@/assets/img/chevron-down_gold.svg') no-repeat;
  width: 30px;
  height: 30px;
  background-size: contain;
}
.filter-dropdown__menu_second {
  z-index: 80;
}
.filter-dropdown__item_second {
  border-left: 1px solid #ffd25a;
  border-right: 1px solid #ffd25a;

  &:last-child {
    border-bottom: 1px solid #ffd25a;
  }
}

.fade-enter-active,
.fade-leave-active {
  transition: 0.3s linear;
}
.fade-enter,
.fade-leave-to {
  transform: translateX(-250px);
  opacity: 0;
}

@media (min-width: 2000px) {
  .slider {
    justify-content: space-evenly;
  }
}
@media (max-width: 1440px) {
  .filter {
    padding: 60px;
    height: 470px;
    margin-bottom: 0;
  }
  .filter__title {
    font-size: 50px;
    line-height: 35px;
  }
  .filter__list {
    margin-top: 35px;
  }
  .filter__list_second {
    margin-top: 50px;
  }
  .filter__leaflets-bg_2 {
    display: none;
  }

  .slider {
    padding: 0 60px 70px;
  }
  .slider__bottom-bg {
    bottom: -930px;
  }
  .swiper {
    width: 290px;
  }
}
@media (max-width: 1200px) {
  .filter__list-item {
    width: 200px;
  }
  .slider {
    flex-direction: column;
  }
  .slider__container {
    width: 100%;
  }
  .slider__bottom-bg {
    bottom: 0;
    height: 540px;
  }
  .slider__tooltip_mobile {
    display: inline-block;
  }
  .swiper {
    height: 110px;
    width: 90%;
    margin-top: 0;
  }
  .swiper .swiper-wrapper {
    padding-left: 20px;
  }
  .button-next {
    left: unset;
    bottom: unset;
    top: 30px;
    right: 20px;
    transform: rotate(-90deg);
  }
  .button-prev {
    top: 30px;
    left: 5px;
    transform: rotate(-90deg);
  }

  .juice-miniature_active {
    .juice-miniature {
      transform: translateX(0);
    }
  }
}
@media (max-width: 1024px) {
  .filter {
    padding: 40px 25px;
  }
  .filter__title {
    font-size: 36px;
  }
  .filter__item-juice-volume {
    font-size: 24px;
  }
  .filter__item-juice-container {
    font-size: 20px;
  }
  .filter__item-name {
    font-size: 20px;
  }
  .filter__leaflets-bg_1 {
    display: none;
  }
  .slider {
    padding: 0 25px 70px;
  }
}
@media (max-width: 1023px) {
  .slider__bottom-bg {
    bottom: 50px;
  }
  .filter {
    height: 425px;
  }
  .filter__list {
    gap: 20px;
  }
  .filter__list-item {
    width: 160px;
  }
}
@media (max-width: 767px) {
  .button-next {
    right: 0;
    z-index: 10;
  }
  .button-prev {
    z-index: 10;
  }
  .slider {
    margin-top: 20px;
  }
  .slider__container {
    display: none;
  }
  .slider__container_mobile {
    display: block;
    position: relative;
    margin-top: 100px;
  }
  .slider__bottom-bg {
    height: 580px;
    bottom: 135px;
  }
  .filter {
    height: 400px;
  }
  .filter__title {
    font-size: 24px;
    line-height: 30px;
  }
  .filter__wave-bg {
    height: 500px;
    top: -187px;
  }
  .filter__list {
    display: none;
  }
  .filter__list_second {
    display: none;
  }
  .filter-dropdown {
    display: inline-block;
  }

  .filter__container_mobile {
    display: flex;
    flex-direction: column;
    gap: 15px;
    margin-top: 25px;
  }
}
@media (max-width: 425px) {
  .juice__image {
    width: 140px;
  }
  .slider {
    margin-top: 0;
  }
  .slider__bottom-bg {
    bottom: 225px;
  }
  .slider__tooltip_mobile {
    font-size: 14px;
    padding: 3px 10px;
  }
  .slider__container_mobile {
    margin-top: 105px;
  }
  .filter-dropdown__toggle {
    font-size: 16px;
  }
  .filter-dropdown__item {
    font-size: 16px;
  }
}
@media (max-width: 375px) {
  .button-next {
    right: -13px;
  }
  .button-prev {
    left: -4px;
  }
}
</style>
