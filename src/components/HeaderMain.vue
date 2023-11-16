<script setup lang="ts">
    import mts_logo from "./icons/mts_logo_large.jpg"
    import search_logo from "./icons/icons8-search-20.png"
    import catalog_logo from "./icons/icons8-burger-bar-24.png"

</script>

<template>
        <div class="header">
            <div class="middle-menu__inner">
                <router-link to="/" class="middle-menu__logo-wrap">
                    <img :src="mts_logo" class="middle-menu__logo"/>
                </router-link>
                <div class="middle-menu__nav">
                    <nav class="main-menu-navigation">
                        <ul class="main-menu-navigation__list">
                            <li class="main-menu-navigation__item">
                                <span class="main-menu-navigation__text">Мобильная связь</span>
                            </li>
                            <li class="main-menu-navigation__item">
                                <span class="main-menu-navigation__text">Для дома</span>
                            </li>
                            <li class="main-menu-navigation__item">
                                <span class="main-menu-navigation__text">Сервисы и подписки</span>
                            </li>
                            <li class="main-menu-navigation__item">
                                <span class="main-menu-navigation__text">Финансы</span>
                            </li>
                            <li class="main-menu-navigation__item">
                                <span class="main-menu-navigation__text">Интернет-магазин</span>
                            </li>
                        </ul>
                    </nav>
                    <div class="middle-menu__search-desktop">
                        <form class="header-search__form">
                            <div class="header-search__btn">
                                <img :src="search_logo" class="header-search__icon" />
                                <div class="header-search__text">Поиск</div>
                            </div>
                        </form>
                    </div>
                </div>
                <div class="middle-menu__right">
                    <button class="middle-menu__btn-login">Войти</button>
                    <button class="middle-menu__btn-catalog">
                        <img :src="catalog_logo" class="middle-menu__catalog-icon"/>
                        <span class="middle-menu__catalog-text">Каталог</span>
                    </button>
                </div>
            </div>
        </div>
</template>

<style>

    .middle-menu__logo-wrap{
        display: flex;
    }
    .header{
        padding: 0px 40px;
        border-bottom: 1px solid rgb(216, 216, 216);
    }

    .middle-menu__inner{
        display: flex;
        align-items: center;
        justify-content: space-between;
        height: 72px;
    }

    .middle-menu__logo{
        width: 44px;
        height: 44px;
    }

    .main-menu-navigation__list {
        display: flex;
        list-style: none;
    }

    .main-menu-navigation__list > li {
        white-space: nowrap;
        font-weight: bold;    
    }

    .main-menu-navigation__text:after{
        content: "";
        height: 2px;
        width: 0;
        background: rgb(242, 33, 96);
        position: absolute;
        left: 10px;
        bottom: -10px;
        transition: 0.3s;
    }

    .main-menu-navigation__text:hover:after{
        width: calc(100% - 20px);
    }

    .main-menu-navigation__text {
        padding: 0px 10px;
        cursor: pointer;
        position: relative;
    }

    .middle-menu__nav {
        flex: 1 1 auto;
        min-width: 0;
        display: flex;
        align-items: center;
        justify-content: space-between;
    }

    .header-search__btn{
        display: flex;
        align-items: center;
    }

    .header-search__text {
        padding-left: 10px;
        color: rgb(133, 124, 124);
    }

    .middle-menu__btn-login{
        margin-left: 16px;
        padding: 13px 13px;
        background-color: #ff0032;
        border-radius: 8px;
        color: white;
        border: none;
        cursor: pointer;
        font-size: 16px;
        font-weight: bold;
    }

    .middle-menu__right{
        display: flex;
        align-items: center;
    }

    .middle-menu__btn-catalog{
       margin-left: 16px;
       padding: 10px;
       background-color: #f2f3f7;
       border: none;
       border-radius: 8px;
       cursor: pointer;
       display: flex;
       align-items: flex-end;
       font-size: 16px;
       font-weight: bold;
    }

    .middle-menu__catalog-text {
        margin: 0px 8px 0px 8px;
    }

</style>