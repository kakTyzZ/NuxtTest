<script setup>
import {ref} from "vue"
import {swiperData} from "../swiperData.js"
import {useCounterStore} from "~/stores/myStore";
import {useBreakpoints} from "~/composables/WindowSizeCheck.js";

const { width } = useBreakpoints()

const store = useCounterStore()
const swiperIndex = ref(0)
const amountOfCards = computed(() => {
    if(width.value !== undefined){
       if (width.value < 480) {
        return 1
    } else if (width.value < 760) {
        return 2
    } else {
        return 3
    } 
    }else{
        return 3
    }
    
})

function nextSlide(){
    if(swiperIndex.value == swiperData.length - 3) return
    swiperIndex.value += 1
    console.log(swiperData.slice(swiperIndex.value,swiperIndex.value+3));
}

function previousSlide(){
    if(swiperIndex.value == 0) return
    swiperIndex.value -= 1
    
}

function addIdToPinia(id){
    store.indexCount = id
}

</script>

<template>
    <div>
        <div class="flex justify-center text-[34px]"> <strong>Документы</strong> </div>
        <div  class="flex gap-[35px] relative mx-5">
            <div class="" v-for="item in swiperData.slice(swiperIndex,swiperIndex+amountOfCards)" :key="item.title">
                <div class="flex flex-col justify-between  max-w-[340px] h-[450px]  w-full px-[25px] py-[10px] shadow-2xl" >
                    <div class="">
                    <div class="title mb-[15px] text-xl md:text-2xl lg:text-3xl">{{ item.title }}</div>
                    <div class="text-xs md:text-sm lg:text-base overflow-hidden max-h-[70%] px-1">{{ item.text }}</div>
                    </div>
                    <NuxtLink @click="addIdToPinia(item.id)" :to="`/documents/${item.id}`"><button class="btn">Перейти</button></NuxtLink>
                </div>
            </div>
                <div
                @click="nextSlide"
                class="max-w-[40px] overflow-hidden absolute right-[-2%] top-[40%] ">
                    <button class="bg-slate-300 w-[80px] h-[80px] rounded-[50%] hover:bg-slate-400">
                    <div class="relative">
                       <svg fill="gray" class="w-[18px] absolute left-[15px] top-[-15px]" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 320 512"><path d="M310.6 233.4c12.5 12.5 12.5 32.8 0 45.3l-192 192c-12.5 12.5-32.8 12.5-45.3 0s-12.5-32.8 0-45.3L242.7 256 73.4 86.6c-12.5-12.5-12.5-32.8 0-45.3s32.8-12.5 45.3 0l192 192z"/></svg> 
                    </div>
                </button>
                </div>
            
                <div
                @click="previousSlide"
                class="max-w-[40px] overflow-hidden absolute left-[-2%] top-[40%] rotate-180 ">
                    <button class=" bg-slate-300 w-[80px] h-[80px] rounded-[50%] hover:bg-slate-400">
                        <div class="relative">
                           <svg fill="gray" class="w-[18px]   absolute left-[15px] top-[-15px]" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 320 512"><path d="M310.6 233.4c12.5 12.5 12.5 32.8 0 45.3l-192 192c-12.5 12.5-32.8 12.5-45.3 0s-12.5-32.8 0-45.3L242.7 256 73.4 86.6c-12.5-12.5-12.5-32.8 0-45.3s32.8-12.5 45.3 0l192 192z"/></svg> 
                        </div>
                </button>
                </div>
        </div>
    </div>
</template>

<style scoped>
.title{
color:#1253A2;

line-height:37.2px ;
font-weight: 700;
}
.text{

line-height: 21.6px;
font-weight: 400;
}
.btn{
    background: #0584FE;
    max-width: 290px;
    height: 45px;
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 0 auto;
    border-radius: 5px;
    color:white;
    font-size: 18px;
}
.btn:hover{
    background: blue
}
</style>