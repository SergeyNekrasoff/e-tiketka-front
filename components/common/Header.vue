<template>
    <div class="header content-flex">
        <div class="row columns">
            <div class="col col-12">
                <div class="header__top">
                    <div class="container">
                        <div class="row align-center">
                            <div class="col col-6">
                                <img  svg-inline src="~/assets/svg/location.svg"/>
                                <span class="location">
                                    Москва
                                </span>
                            </div>
                            <div class="col col-6">
                                <div class="header__about">
                                    <ul class="header__about-list">
                                        <li><nuxt-link to="/" class="default-link">О магазине</nuxt-link></li>
                                        <li><nuxt-link to="/" class="default-link">Доставка</nuxt-link></li>
                                        <li><nuxt-link to="/" class="default-link">Оплата</nuxt-link></li>
                                        <li><a href="tel:8 800 845-88-00" class="default-link">8 800 845-88-00</a></li>
                                    </ul>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <div class="col col-12">
                <div class="header__middle">
                    <div class="container">
                        <div class="row align-center justify">
                            <div class="col">
                                <div class="logo">
                                    <nuxt-link to="/">
                                        <img  svg-inline src="~/assets/svg/logo.svg"/>
                                    </nuxt-link>
                                </div>
                            </div>
                            <div class="col search">
                                <input
                                    v-model="search"
                                    class="input-text input-text--round"
                                    placeholder="Поиск среди 34 000 товаров…"
                                    @keyup.enter="search"
                                    type="text">
                                <button class="btn btn-search">
                                    <img svg-inline src="~/assets/svg/search.svg" />
                                </button>
                            </div>
                            <div class="col">
                                <div class="profile">
                                    <img  class="profile__icon" svg-inline src="~/assets/svg/profile.svg"/>
                                    <nuxt-link to="/" class="link link-profile">Личный кабинет</nuxt-link>
                                </div>
                            </div>
                            <div class="col">
                                <div class="cart">
                                    <nuxt-link to="/" class="default-link default-link--round default-link-cart">
                                        <img class="cart__icon" svg-inline src="~/assets/svg/cart.svg"/>
                                        <span>Корзина</span>
                                    </nuxt-link>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <div class="col col-12">
                <div class="header__bottom">
                    <div class="container">
                        <div class="row align-center justify">
                            <div class="col header__menu">
                                <button class="btn btn-default">Все категории</button>
                            </div>
                            <div class="col header__navigation">
                                <div class="row align-center justify">
                                    <nuxt-link 
                                        class="default-link menu-item"
                                        :to="`/${category.name}`" 
                                        v-for="(category, index) in categories" 
                                        :key="index">
                                        {{ category.name }}
                                    </nuxt-link>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            search: '',
            categories: [{
                name: 'Смартфоны и гаджеты',
                path: '/'
            }, {
                name: 'Телевизоры, аудио-видео',
                path: '/'
            }, {
                name: 'Бытовая техника',
                path: '/'
            }, {
                name: 'Компьютеры и комлектующие',
                path: '/'
            }, {
                name: 'Товары для спорта',
                path: '/'
            }, {
                name: 'Строительство и ремонт',
                path: '/'
            }]
        }
    },
    watch: {
        'search': function(oldValue, newValue) {
            if (oldValue !== newValue) {
                console.log(this.search)
            }
        }
    }
}
</script>

<style lang="scss" scoped>
.header {
    box-shadow: 0 2px 4px 0 rgba(0, 0, 0, .1);
    color: #fff;
    overflow: hidden;
    
    &__top {
        background: $redDark;
        height: 48px;
    }

    &__middle {
        background: $red;
        height: 79px;
    }

    &__bottom {
        background: $white;
        height: 68px;
    }

    .location {
        padding-left: 16px;
    }

    &__about {
        text-align: right;

        &-list li {
            display: inline-block;
            margin-left: 30px;
            color: #fff;

            &:last-child {
                margin-left: 63px;
            }

            .default-link {
                font-size: 14px;
            }
        }
    }

    .logo {
        width: 138px;
        margin-right: 39px;
    }

    .search {
        position: relative;
        width: calc(100% - 580px);
        margin-right: 43px;

        .input-text {
            width: 100%;
        }

        .btn-search {
            position: absolute;
            top: 0;
            right: 8px;
        }
    }

    .profile {
        margin-right: 39px;

        &__icon {
            border-radius: 50%;
            width: 18px;
            height: 18px;
            margin-right: 14px;
        }
    }

    .link-profile {
        vertical-align: top;
        color: #fff;
    }

    .cart {
        &__icon {
            width: 18px;
            height: 16px;
            margin-right: 16px;
        }

        .default-link-cart {
            display: flex;
            border: 1px solid #fff;
            width: 166px;
            align-items: center;
            justify-content: center;
        }
    }

    &__menu {
        border-right: 1px solid rgba(0, 0, 0, .1);
        width: 180px;

        .btn-default {
            color: #000;
            position: relative;
            padding-left: 53px;

            &::before {
                content: '';
                background: url('~assets/svg/burger.svg') no-repeat;
                width: 25px;
                height: 20px;
                display: inline-block;
                position: absolute;
                left: 0px;
                top: 10px;
            }
        }
    }

    &__navigation {
        width: calc(100% - 210px);

        .menu-item {
            font-size: 13px;
            color: #000;
        }
    }
}
</style>