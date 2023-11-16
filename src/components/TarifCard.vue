<script setup lang="ts">
import simcard_icon from "./icons/icons8-sim-card-24.png"
import phone_icon from "./icons/icons8-phone-24.png"
import tv_icon from "./icons/icons8-tv-24.png"
import wifi_icon from "./icons/icons8-wifi-24.png"

const props = defineProps({
    name: String,
    description: String,
    gigabytes: Number,
    minutes: Number,
    television: Number,
    speed: Number,
    price: Number
})

</script>

<template>
    <div class="card__wrapper">
        <div class="card__body">
            <span class="card__title">{{ props.name }}</span>
            <div class="card__description">{{ props.description }}</div>
            <ul class="card__list-features">
                <li class="card__feature" v-if="props.gigabytes !== 0">
                    <img class="card__img" :src="simcard_icon"/>
                    <span class="card-feature__text">{{ props.gigabytes }} ГБ</span>
                </li>
                <li class="card__feature" v-if="props.minutes !== 0">
                    <img class="card__img" :src="phone_icon"/>
                    <span class="card-feature__text">{{ props.minutes }} минут</span>
                </li>
                <li class="card__feature" v-if="props.television !== 0">
                    <img class="card__img" :src="tv_icon"/>
                    <span class="card-feature__text">{{ props.television }} ТВ</span>
                </li>
                <li class="card__feature">
                    <img class="card__img" :src="wifi_icon"/>
                    <span class="card-feature__text">{{ props.speed }} Мбит/с</span>
                </li>              
            </ul>
        </div>
        <div class="card__footer">
            <span class="card__price">{{ props.price }} ₽/мес</span>
            <div class="card-actions__wrapper">
                <div class="card__button">Подключить</div>
                <div class="card__button-secondary">Подробнее</div>
            </div>
        </div>
    </div>

</template>

<style scoped>

.card__wrapper {
    height: 100%;
    display: flex;
    flex-direction: column;
    border-radius: 24px;
    box-shadow: 0 6px 24px rgba(15,34,79,.14);
    cursor: pointer;
    transition: box-shadow .3s ease-in-out;
}
.card__body {
    padding: 20px 20px 28px;
}

.card__title {
    font-size: 20px;
    font-weight: bold;
}

.card__description {
    margin-top: 6px;
}

.card__list-features {
    list-style: none;
    padding-left: 0;
}

.card__feature {
    display: flex;
    align-items: center;
}

.card__feature:not(:first-child){
    margin-top: 6px;
}

.card__feature:last-child{
    margin-top: 16px;
}

.card-feature__text {
    font-size: 17px;
    font-weight: bold;
}

.card__img {
    padding-right: 10px;
}

.card__price {
    font-size: 17px;
    font-weight: bold;
}

.card__button {
    height: 44px;
    line-height: 24px;
    padding: 10px 10px;
    background-color: rgb(255,0,50);
    color: white;
    font-size: 15px;
    font-weight: 600;
    font-family: 'Open Sans', Helvetica, Arial, sans-serif;
    border-radius: 8px;
    border: none;
    cursor: pointer;
    width: 100%;
    display: flex;
    justify-content: center;
}

.card__button-secondary {
    height: 44px;
    line-height: 24px;
    padding: 10px 10px;
    background-color: #f2f3f7;
    color:#1d2023;
    font-size: 15px;
    font-weight: 600;
    font-family: 'Open Sans', Helvetica, Arial, sans-serif;
    border-radius: 8px;
    border: none;
    cursor: pointer;
    width: 100%;
    display: flex;
    justify-content: center;
}

.card__footer {
    padding: 0px 20px;
    margin-top: auto;
}

.card-actions__wrapper {
    margin-top: 12px;
    display: flex;
    gap: 8px;
    width: 100%;
}

.card__footer>:last-child {
    margin-bottom: 20px;
}

</style>