<script setup lang="ts">
import { onMounted, reactive } from "vue";
import HeaderMain from "../components/HeaderMain.vue"
import TarifCard from "@/components/TarifCard.vue";
import baseURL from "@/router/baseURL";

interface Tarif {
    id: bigint,
    name: string,
    description: string,
    gigabytes: number,
    minutes: number,
    television: number,
    speed: number,
    price: number
}

const tarifs:Array<Tarif> = reactive([])

onMounted( () => {

    fetch(baseURL + "/tarifs/all", {
                method:"GET",
            })
    .then((response) => {
        if (response.ok) {
            return response.json();
        }
    })
    .then((result:Array<Tarif>) => {

        const iterator = result.values();
        for (const item of iterator) {
            tarifs.push(item);
        }
    })
    .catch((error) => {
        console.error(error);
    });

})

</script>

<template>

    <HeaderMain/>
    <div class="main">
        <div class="tarifs__main-heading">Тарифы и подписки</div>
        <div class="tarifs__content">
            <TarifCard v-for="tarif in tarifs" :key="tarif.id.toString"
                :name = "tarif.name"
                :description = "tarif.description"
                :gigabytes = "tarif.gigabytes"
                :minutes = "tarif.minutes"
                :television = "tarif.television"
                :speed = "tarif.speed"
                :price = "tarif.price"
            />
        </div>
    </div>
    <div class="footer">

    </div>

</template>

<style scoped>

.footer {
  margin: 0px 80px;
}

.tarifs__main-heading {
    font-size: 50px;
    padding: 40px 80px;
}

.tarifs__content {
    padding: 0px 80px 40px 80px;
    display: grid;
    gap: 32px;
}


@media(min-width: 1280px){
    .tarifs__content {
        grid-template-columns: repeat(4, 1fr);
    }
}

@media(max-width < 1280px){
    .tarifs__content {
        grid-template-columns: repeat(2, 1fr);
    }
}

</style>