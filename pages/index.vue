<template>
  <div class="main">
    <div class="hero content-flex">
      <client-only>
        <swiper class="swiper" :options="heroOption">
          <swiper-slide>
            <div class="hero__item">
              <img src="~/assets/images/slide1.png" alt="" />
            </div>
          </swiper-slide>
          <swiper-slide>
            <div class="hero__item">
              <img src="~/assets/images/slide1.png" alt="" />
            </div>
          </swiper-slide>
          <swiper-slide>
            <div class="hero__item">
              <img src="~/assets/images/slide1.png" alt="" />
            </div>
          </swiper-slide>
          <div class="swiper-pagination" slot="pagination"></div>
        </swiper>
      </client-only>
    </div>

    <div class="advanteges">
      <div class="container">
        <div class="row columns">
          <div class="col col-12">
              <h1 class="title">Совершать выгодные покупки — это легко</h1>
          </div>
          <div class="advanteges__group col col-12">
            <div class="row align-center center">
              <div class="col col-4">
                <div class="advanteges__item">
                  <img svg-inline src="~/assets/svg/touch-hand-gesture-tap-double-tap.svg" alt="" class="advanteges__img"/>
                  <div class="advanteges__text">Выберите понравившийся товар на сайте</div>
                </div>
              </div>
              <div class="col col-4">
                <div class="advanteges__item">
                  <img svg-inline src="~/assets/svg/001-credit-card.svg" alt="" class="advanteges__img"/>
                  <div class="advanteges__text">Оплатите заказ баллами или картой прямо на сайте</div>
                </div>
              </div>
              <div class="col col-4">
                <div class="advanteges__item">
                  <img svg-inline src="~/assets/svg/delivery-truck.svg" alt="" class="advanteges__img"/>
                  <div class="advanteges__text">И мы доставим ваш заказ как можно быстрее</div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

    </div>

    <div class="carousel carousel-cards">
      <div class="container">
        <div class="row columns">
          <div class="col col-12">
              <h2 class="title">Стоит присмотреться</h2>
          </div>
          <div class="col col-12">
            <client-only>
              <swiper 
                class="swiper" 
                :options="itemsOption">
                <swiper-slide
                  class="item-card"
                  v-for="item in newItems" :key="item.id">
                  <img class="item-card__img" :src="require(`~/assets/images/items/${item.img}`)" alt="" />
                  <star-rating 
                    class="rating"
                    v-model="item.rating"
                    :show-rating="false"
                    :border-width="0"
                    :star-size="14"
                    :padding="2"
                    :rounded-corners="false" 
                    :read-only="false"
                    :star-points="[23,2, 14,17, 0,19, 10,34, 7,50, 23,43, 38,50, 36,34, 46,19, 31,17]"
                    inactive-color="#d5d3d3"
                    active-color="#ffc400"/>
                  <div class="item-card__title">
                    {{ item.title }}
                  </div>
                  <div class="item-card__price">от <b>{{ item.price }}</b> ₽ в мес.</div>
                  <div class="item-card__old-price">{{ item.oldPrice }} ₽</div>
                  <button class="btn btn-default btn-add-to-cart">
                    Добавить в корзину
                  </button>
                </swiper-slide>
                <div class="swiper-button-prev btn-prev" slot="button-prev"></div>
                <div class="swiper-button-next btn-next" slot="button-next"></div>
              </swiper>
            </client-only>
          </div>
        </div>
      </div>
    </div>

    <div class="categories">
      <div class="container">
        <div class="row columns">
          <div class="col col-12">
              <h3 class="title">Рекомендуемые категории</h3>
          </div>
          <div class="col col-12">
            <client-only>
              <swiper 
                class="swiper" 
                :options="categoriesOption">
                <swiper-slide
                  class="category-item"
                  v-for="category in categories" :key="category.id">
                  <nuxt-link class="default-link" to="/">
                    <div class="category-item__img">
                      <img class="item-card__img" :src="require(`~/assets/images/items/${category.img}`)" alt="" />
                    </div>
                    <div class="category-item__title">
                      {{ category.name }}
                    </div>
                  </nuxt-link>
                </swiper-slide>
                <div class="swiper-button-prev btn-prev" slot="button-prev"></div>
                <div class="swiper-button-next btn-next" slot="button-next"></div>
              </swiper>
            </client-only>
          </div>
        </div>
      </div>
    </div>

    <div class="cta-block">
      <div class="container">
        <div class="row columns cta-block--background">
          <div class="col">
            <h3 class="title">Для экономии не нужен повод, скидки на популярные товары самых разных категорий.</h3>
          </div>
          <div class="col">
            <nuxt-link class="default-link btn btn-default btn-round btn-cta" to="/">Вперёд к покупкам!</nuxt-link>
          </div>
        </div>
      </div>
    </div>

    <div class="new-items">
      <div class="container">
        <div class="row columns">
          <div class="col col-12">
            <h3 class="title">Новые товары</h3>
          </div>
          <div class="col col-12">
            <div class="row nowrap align-top justify">
              <div 
                class="col item-card"
                v-for="item in newItems" :key="item.id">
                <img class="item-card__img" :src="require(`~/assets/images/items/${item.img}`)" alt="" />
                <star-rating 
                  class="rating"
                  v-model="item.rating"
                  :show-rating="false"
                  :border-width="0"
                  :star-size="14"
                  :padding="2"
                  :rounded-corners="false" 
                  :read-only="false"
                  :star-points="[23,2, 14,17, 0,19, 10,34, 7,50, 23,43, 38,50, 36,34, 46,19, 31,17]"
                  inactive-color="#d5d3d3"
                  active-color="#ffc400"/>
                <div class="item-card__title">
                  {{ item.title }}
                </div>
                <div class="item-card__price">от <b>{{ item.price }}</b> ₽ в мес.</div>
                <div class="item-card__old-price">{{ item.oldPrice }} ₽</div>
                <button class="btn btn-default btn-add-to-cart">
                  Добавить в корзину
                </button>
              </div>
            </div>
            <button class="btn btn-default btn-more">Показать еще</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: 'E-tiketka | Главная',
    }
  },
  data() {
    return {
      windowWidth: '',
      heroOption: {
        slidesPerView: 'auto',
        spaceBetween: 0,
        initialSlide: 1,
        pagination: {
          el: '.swiper-pagination',
          clickable: true
        }
      },
      itemsOption: {
        slidesPerView: 5,
        spaceBetween: 20,
        navigation: {
          nextEl: '.btn-next',
          prevEl: '.btn-prev'
        }
      },
      categoriesOption: {
        slidesPerView: 5,
        spaceBetween: 20,
        navigation: {
          nextEl: '.btn-next',
          prevEl: '.btn-prev'
        }
      },
      rating: 0,
      items: [{
          id: 1,
          img: 'iphone.png',
          rating: 4,
          title: 'Смартфон Apple iPhone 11 Pro 64GB золотой (MWC52RU/A)',
          price: '13000',
          oldPrice: '36000'
        }, {
          id: 2,
          img: 'laptop.png',
          rating: 4,
          title: 'Холодильник Gorenje NRK6201MX серебристый (двухкамерный)',
          price: '13000',
          oldPrice: '36000'
        }, {
          id: 3,
          img: 'some1.png',
          rating: 5,
          title: 'Планшет Apple iPad Pro 11 64Gb Wi-Fi silver',
          price: '13000',
          oldPrice: '36000'
        }, {
          id: 4,
          img: 'some2.png',
          rating: 2,
          title: 'Планшет Apple iPad Air (2019) 64Gb Wi-Fi space grey',
          price: '13000',
          oldPrice: '36000'
        }, {
          id: 5,
          img: 'some7.png',
          rating: 5,
          title: 'Геймпад Microsoft Xbox One Controller черный',
          price: '13000',
          oldPrice: '36000'
        }, {
          id: 6,
          img: 'some5.png',
          rating: 1,
          title: 'Аккумулятор Xiaomi Mi Power Bank 2S (2i) 10000 серебристый',
          price: '13000',
          oldPrice: '36000'
        },
        {
          id: 7,
          img: 'some4.png',
          rating: 3,
          title: 'Посудомоечная машина Electrolux ESL 94320 LA',
          price: '13000',
          oldPrice: '36000'
      }],
      newItems: [{
          id: 1,
          img: 'iphone.png',
          rating: 4,
          title: 'Смартфон Apple iPhone 11 Pro 64GB золотой (MWC52RU/A)',
          price: '13000',
          oldPrice: '36000'
        }, {
          id: 2,
          img: 'laptop.png',
          rating: 4,
          title: 'Холодильник Gorenje NRK6201MX серебристый (двухкамерный)',
          price: '13000',
          oldPrice: '36000'
        }, {
          id: 3,
          img: 'some1.png',
          rating: 5,
          title: 'Планшет Apple iPad Pro 11 64Gb Wi-Fi silver',
          price: '13000',
          oldPrice: '36000'
        }, {
          id: 4,
          img: 'some2.png',
          rating: 2,
          title: 'Планшет Apple iPad Air (2019) 64Gb Wi-Fi space grey',
          price: '13000',
          oldPrice: '36000'
        }, {
          id: 5,
          img: 'some7.png',
          rating: 5,
          title: 'Геймпад Microsoft Xbox One Controller черный',
          price: '13000',
          oldPrice: '36000'
        }, {
          id: 6,
          img: 'some5.png',
          rating: 1,
          title: 'Аккумулятор Xiaomi Mi Power Bank 2S (2i) 10000 серебристый',
          price: '13000',
          oldPrice: '36000'
        }, {
          id: 7,
          img: 'some4.png',
          rating: 3,
          title: 'Посудомоечная машина Electrolux ESL 94320 LA',
          price: '13000',
          oldPrice: '36000'
        }, {
          id: 8,
          img: 'iphone.png',
          rating: 4,
          title: 'Смартфон Apple iPhone 11 Pro 64GB золотой (MWC52RU/A)',
          price: '13000',
          oldPrice: '36000'
        }, {
          id: 9,
          img: 'laptop.png',
          rating: 4,
          title: 'Холодильник Gorenje NRK6201MX серебристый (двухкамерный)',
          price: '13000',
          oldPrice: '36000'
        }, {
          id: 10,
          img: 'some1.png',
          rating: 5,
          title: 'Планшет Apple iPad Pro 11 64Gb Wi-Fi silver',
          price: '13000',
          oldPrice: '36000'
      }],
      categories: [{
          id: 1,
          img: 'some4.png',
          name: 'Мобильные телефоны'
        }, {
          id: 2,
          img: 'some18.png',
          name: 'Теливизоры'
        }, {
          id: 3,
          img: 'some5.png',
          name: 'Компьютерная техника и аксессуары'
        }, {
          id: 4,
          img: 'some6.png',
          name: 'Игровые приставки'
        }, {
          id: 5,
          img: 'some7.png',
          name: 'Умный дом'
        }, {
          id: 6,
          img: 'some7.png',
          name: 'Компьютерная техника и аксессуары'
        }, {
          id: 7,
          img: 'some2.png',
          name: 'Компьютерная техника и аксессуары'
        }, {
          id: 8,
          img: 'some8.png',
          name: 'Компьютерная техника и аксессуары'
        }, {
          id: 9,
          img: 'some3.png',
          name: 'Компьютерная техника и аксессуары'
      }]
    }
  },
  created() {
    if (process.browser) {
      window.addEventListener('resize', this.handleResize)
      this.handleResize()
    }
  },
  destroyed() {
    if (process.browser) {
      window.removeEventListener('resize', this.handleResize)
    }
  },
  methods: {
    handleResize() {
        this.windowWidth = window.innerWidth;
    }
  }
}
</script>

<style lang="scss" scoped>
.hero {
  margin-top: 20px;

  &__item {
    width: 60vw !important;
    min-height: 330px;
    border-radius: 9px;
    margin-right: 20px !important;
    overflow: hidden;
  }
}

.advanteges {
  margin-bottom: 40px;

  &__group {
    height: 169px;
    border-radius: 9px;
    background-color: $white;
  }

  &__item {
    display: flex;
    flex-direction: row;
    flex-wrap: nowrap;
    justify-content: center;
    align-content: stretch;
    align-items: center;
  }

  &__img,
  &__text {
    display: flex;
  }

  &__text {
    font-size: 14px;
    line-height: 1.64;
    max-width: 180px;
  }

  &__img {
    margin-right: 40px;
  }
}

.carousel-cards {
  margin-bottom: 40px;

  .item-card {
    margin-right: 20px;
  }
}

.item-card {
  width: 245px !important;
  min-height: 427px;
  max-width: 20%;
  border-radius: 9px;
  background-color: $white;
  padding: 20px;
  text-align: center;
  overflow: hidden;

  &__img {
    max-width: 100%;
  }

  .rating {
    margin: 40px 0 12px;
  }

  &__title {
    font-size: 14px;
    line-height: 1.43;
    color: #000;
    text-align: left;
    margin-bottom: 20px;
    min-height: 60px;
  }

  &__price {
    font-size: 14px;
    line-height: 1.43;
    text-align: left;

    b {
      font-size: 14px;
      line-height: 1;
    }
  }

  &__old-price {
    font-size: 13px;
    opacity: .61;
    text-align: left;
    margin: 8px 0 16px;
  }
}

.categories {
  margin-bottom: 40px;
}

.category-item {
  width: 245px !important;
  height: 263px;
  border-radius: 9px;
  background-color: $white;
  padding: 20px;
  text-align: center;
  color: #000;
  transition: .3s ease-in-out;
  overflow: hidden;

  &:hover {
    box-shadow: 0 2px 4px 0 rgba(0, 0, 0, .1);
  }

  &__img {
    width: 100%;
    min-height: 140px;
    margin-bottom: 36px;
    overflow: hidden;
  }

  &__title {
    font-size: 14px;
    line-height: 1.43;
    color: #000;
    height: 43px;
  }
}

.cta-block {
  margin-bottom: 40px;

  &--background {
    border-radius: 9px;
    height: 324px;
    box-shadow: 6px 6px 24px 0 rgba(233, 74, 78, 0.36);
    background: rgb(2,0,36);
    background: linear-gradient(99deg, rgba(2,0,36,1) 0%, rgba(235,131,32,0.6110819327731092) 0%, rgba(235,74,78,1) 90%);
  }

  .title {
    width: 442px;
    margin-left: 120px;
    text-align: left;
    color: $white;
  }
}

.new-items {
  padding-bottom: 40px;
  
  .item-card {
    margin-bottom: 20px;
  }
}

.btn-add-to-cart {
  width: 100%;
  border-radius: 18px;
  background-color: #ec3752;
}

.swiper-button-next, .swiper-button-prev {
    transition: opacity .5s;
}

.swiper-button-disabled {
     opacity: 0 !important;
}

.btn-cta {
  display: block;
  margin-left: 120px;
  width: 223px;
  border-radius: 18px;
  background-color: $white;
  font-size: 12px;
  color: #000;
}

.btn-more {
  border-radius: 7px;
  background-color: rgba(236, 55, 82, .1);
  width: 100%;
  text-align: center;
  color: #000;
}
</style>
