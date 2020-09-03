<template functional>
    <div class="footer content-flex">
        <div class="row columns">
            <div class="col col-12">
                <div class="footer__top">
                    <div class="container">
                        <div class="row align-center justify">
                            <div class="col col-2">
                                <div class="logo">
                                    <nuxt-link to="/">
                                        <img  svg-inline src="~/assets/svg/logo.svg"/>
                                    </nuxt-link>
                                </div>
                            </div>

                            <div class="col col-7">
                                <div class="row align-center justify">
                                    <div class="col">
                                        <ul class="footer__list">
                                            <li>
                                                <nuxt-link class="default-link" to="/">О магазине</nuxt-link>
                                            </li>
                                            <li>
                                                <nuxt-link class="default-link" to="/">Доставка</nuxt-link>
                                            </li>
                                        </ul>
                                    </div>
                                    <div class="col">
                                        <ul class="footer__list">
                                            <li>
                                                <nuxt-link class="default-link" to="/">Оплата</nuxt-link>
                                            </li>
                                            <li>
                                                <nuxt-link class="default-link" to="/">Обратная связь</nuxt-link>
                                            </li>
                                        </ul>
                                    </div>
                                    <div class="col">
                                        <ul class="footer__list">
                                            <li>
                                                <nuxt-link class="default-link" to="/">Публичная оферта</nuxt-link>
                                            </li>
                                            <li>
                                                <nuxt-link class="default-link" to="/">Политика конфиденциальности</nuxt-link>
                                            </li>
                                        </ul>
                                    </div>

                                </div>
                            </div>

                            <div class="col col-3 footer__top--right">
                                <ul class="footer__list">
                                    <li>
                                        <a href="tel:8 800 845-88-00" class="default-link footer-tel-link">8 (800) 845-88-00</a>
                                    </li>
                                    <li>
                                        <nuxt-link class="default-link" to="/">Политика конфиденциальности</nuxt-link>
                                    </li>
                                </ul>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="col col-12">
                <div class="footer__bottom">
                    <div class="container">
                        <span class="copy">Товары на сайте реализуются ООО "{{ props.company }}" © {{ props.year }}</span>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.footer {
    &__top {
        background: $red;
        height: 257px;

        &--right {
            text-align: right;
        }
    }

    &__bottom {
        background: $redDark;
        height: 53px;
    }

    .logo {
        width: 138px;
        margin-right: 39px;
        margin-top: -29px;
    }

    &__list li {
        margin-bottom: 20px;

        &:last-child {
            margin-bottom: 0;
        }

        .default-link {
            font-size: 13px;
            line-height: 1.54;
        }

        .footer-tel-link {
            font-family: 'Averta-Bold';
            font-size: 24px;
            line-height: 0.83;
        }
    }

    .copy {
        font-size: 14px;
        line-height: 1.43;
        color: $white;
        opacity: .75;
    }
}
</style>