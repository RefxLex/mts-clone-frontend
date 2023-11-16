<script setup lang="ts">
import HeaderMain from "../components/HeaderMain.vue";
import simcard_icon from "../components/icons/sim.png";
import wifi_icon from "../components/icons/icons8-wifi-94.png";
import play_button_icon from "../components/icons/icons8-play-button-94.png";
import options_icon from "../components/icons/menu.png";

</script>

<template>

  <HeaderMain/>
  <div class="main">
    <section class="section-box__navigations">
      <div class="navigations__wrapper">
        <div class="navigations">
          <div class="navigations__cards-wrapper">
              <router-link to="/tarif" class="navigations__card">
                  <div class="card__left-content">
                    <img class="card__img" :src="simcard_icon"/>
                  </div>
                  <span class="card__right-content">Тарифы и&nbsp;подписки</span>
              </router-link>
              <a class="navigations__card">
                  <span class="card__left-content">
                    <img class="card__img" :src="options_icon"/>
                  </span>
                  <span class="card__right-content">Услуги <br> и&nbsp;опции</span>
              </a>
              <a class="navigations__card">
                  <span class="card__left-content">
                    <img class="card__img" :src="wifi_icon"/>
                  </span>
                  <span class="card__right-content">Домашний <br> интернет и&nbsp;ТВ</span>
              </a>
              <a class="navigations__card">
                  <span class="card__left-content">
                    <img class="card__img" :src="play_button_icon"/>
                  </span>
                  <span class="card__right-content">Сервисы <br> и&nbsp;развлечения</span>
              </a>
          </div>
        </div>
      </div>
    </section>
  </div>
  <div class="footer"></div>

</template>


<style scoped>
.main {
  margin: 20px 40px;
}
.footer {
  margin: 0px 40px;
}

.section-box__navigations {
  padding: 60px 0px;
}

.navigations__wrapper {
  padding: 0px 40px;
  width: clamp(320px, 100%, 1680px);
}

.navigations__cards-wrapper{
  display: flex;
  justify-content: space-between;
  flex-wrap: nowrap;
}

.navigations__card {
    width: calc((100% / 4) - (96px / 4));
    margin-right: 32px;
    display: flex;
    flex-wrap: nowrap;
    border-radius: 16px;
    transition: .3s;
    cursor: pointer;
    align-items: center;
    box-shadow: 0 0 16px rgba(0,0,0,.08), 0 4px 16px rgba(0,0,0,.08);
    text-decoration: none;
    color: black;
    padding: 15px 30px;
}

@media screen and (max-width: 1279px){
  .section-box__navigations .navigations .navigations__card {
      flex-direction: column;
      border-radius: 24px;
  }
  .card__right-content {
    padding: 10px 10px;
  }
}

@media (min-width: 1280px){

  .navigations__card{
    justify-content: left;
  }
  .card__left-content { 
    padding-right: 20px;
  }
}

.card__right-content {
  text-align: center;
  font-size: 14px;
  line-height: 20px;
  font-weight: 600;
}

.card__img {
  height: 60px;
  width: 60px;
}

</style>