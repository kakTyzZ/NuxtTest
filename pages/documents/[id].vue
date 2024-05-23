<script setup>
import { swiperData } from "~/swiperData";

import {useCounterStore} from "~/stores/myStore";

const store = useCounterStore()

console.log(store.indexCount);


</script>



<template>
    <div v-if="store.indexCount" class="max-w-[1156px] w-full mx-auto ">
        <div class="title mb-[40px]"> <strong>{{ swiperData[store.indexCount-1].title }}</strong></div>

        <div>
            <h3 class="title">Заголовок 1</h3>
            <div class="text">{{ swiperData[store.indexCount-1].text }}</div>
        </div>
        <div>
            <h3 class="title">Заголовок 2</h3>
            <div class="text">{{ swiperData[store.indexCount-1].text }}</div>
        </div>
        <div>
            <h3 class="title">Заголовок 3</h3>
            <div class="text">{{ swiperData[store.indexCount-1].text }}</div>
        </div>
    </div>
</template>

<style scoped>
.title{
font-size: 41px;
margin-bottom: 25px;
}

.text{
    font-size: 18px;
}
</style>