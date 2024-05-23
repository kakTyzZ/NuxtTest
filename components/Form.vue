<script setup>
import {ref,onMounted} from "vue"

const redClassForInput = ref('shadow-[inset_0_0_0_2px] shadow-red-300')
const showPopUp = ref(false)
const showModal = ref(false)
const formData = ref({
    carNumber: '',
    region: '',
    TC:'',
})

function watchVideo(){
    showModal.value = true
}
function closeModal(){
    showModal.value = false
}

function submitForm(){
    if(formData.value.carNumber == ''){
        const iii = document.querySelector('#carNumber')
    iii.classList.value = `carInput ${redClassForInput.value}`
    setTimeout(()=>iii.classList.value = "carInput",1500)
    return
    }
    if(formData.value.region == ''){
        const iii = document.querySelector('#region')
    iii.classList.value = `regionInput ${redClassForInput.value}`
    setTimeout(()=>iii.classList.value = "regionInput",1500)
        return
}
    if(formData.value.TC == ''){
        const iii = document.querySelector('#TC')
    iii.classList.value = `TcInput ${redClassForInput.value}`
    setTimeout(()=>iii.classList.value = "TcInput",1500)
        return 
    }
    showPopUp.value = true
    setTimeout(()=>showPopUp.value = false,1500)
    
    setTimeout(()=>{formData.value = {
        carNumber: '',
        region: '',
        TC:'',
    }},2000)
    
       
}

function showInputClasses(event){
    const element = event.target
    const style = getComputedStyle(element)
    console.log(style);
    
    let placeHolder = ""
    for (let key in style) {
    if (style.hasOwnProperty(key)) {
        const arr = []
        arr.push(key,style[key])
        placeHolder += arr
        }
        }
    element.placeholder = placeHolder
}

onMounted(() => {
    formData.value = {
        carNumber: '',
        region: '',
        TC:'',
    }
})

</script>

<template>
    <div class="container">
        <div>
            <div>
                <div v-if="showPopUp" class="flex m-auto flex-justify-center fixed top-0 left-0 right-0 bottom-0 w-[500px] h-[300px] bg-white border-black-300 border-4 shadow-2xl text-3xl rounded-2xl">
                    <p class="m-auto text-5xl  z-10">
                        <ul class="text-black">
                            <li class="text-black">{{ formData.carNumber }}</li>
                            <li class="text-black">{{ formData.region }}</li>
                            <li class="text-black">{{ formData.TC }}</li>
                        </ul>
                    </p>
                </div>
            </div>
            <div v-if="showModal" class="modalBG">
                <div class="modalContainer">
                    <div>
                        <button @click="closeModal" class="modalCloseBtn">Закрыть</button>
                    </div>
                    <div class="mt-10 h-full">
                        <video controls width="100%" height="100%">
                            <source src="~/assets/a1.mp4" type="video/mp4">
                        </video>

                    </div>
                </div>
            </div>
            <form @click.prevent class="form">
                <div class="title">
                    <strong>Проверьте штарафы и зарегистрируйтесь в 1 клик</strong>
                    </div>
                <div class="inputContainer">
                    <div >
                        <label for="carNumber" class="label">Номер автомобиля</label>
                        <input @focus="showInputClasses" v-model="formData.carNumber" required class="carInput"  placeholder="" type="text" id="carNumber">
                    </div>
                    <div class="regionContainer">
                        <label class="label" for="region">Регион</label>
                        <input @focus="showInputClasses" v-model="formData.region" required class="regionInput" type="text" id="region">
                    </div>
                </div>
                <div class="">
                    <label class="label" for="TC">Свидетельство о регистрации ТС</label>
                    <input @focus="showInputClasses" v-model="formData.TC" required class="TcInput" type="text" id="TC">
                </div>
                <div class="btnContainer">
                    <div class=" btnFinesContainer">
                         <button @click="submitForm" class="btnFines">Проверить штрафы
                    </button>
                    <svg fill="white" class="w-[18px] " xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><path  d="M438.6 278.6c12.5-12.5 12.5-32.8 0-45.3l-160-160c-12.5-12.5-32.8-12.5-45.3 0s-12.5 32.8 0 45.3L338.8 224 32 224c-17.7 0-32 14.3-32 32s14.3 32 32 32l306.7 0L233.4 393.4c-12.5 12.5-12.5 32.8 0 45.3s32.8 12.5 45.3 0l160-160z"/></svg>
                    </div>
                   
                    <div class="hover:shadow-2xl hover:bg-slate-100" >
                        <button @click="watchVideo" class="btnServiceContainer">
                        <svg
                        fill="blue" class="w-[25px]"
                        xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><path d="M464 256A208 208 0 1 0 48 256a208 208 0 1 0 416 0zM0 256a256 256 0 1 1 512 0A256 256 0 1 1 0 256zM188.3 147.1c7.6-4.2 16.8-4.1 24.3 .5l144 88c7.1 4.4 11.5 12.1 11.5 20.5s-4.4 16.1-11.5 20.5l-144 88c-7.4 4.5-16.7 4.7-24.3 .5s-12.3-12.2-12.3-20.9V168c0-8.7 4.7-16.7 12.3-20.9z"/></svg>
                        <div class="btnAboutService">О сервисе (1 мин. 20сек)</div>
                        </button>
                        
                        
                    </div>
                    
                </div>

                <div>Нажимая Проверить штрафы вы соглашаетесь с политикой обработки персональных данных и принимаете оферту</div>
            </form>
        </div>
        <div class="imgContainer">
            <img src="~/assets/image1.png" alt="">
        </div>
        
    </div>
    
</template>

<style scoped>
.modalBG{
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.5);
    display: flex;
    justify-content: center;
    align-items: center;
   
}
.modalContainer{
    z-index:100;
    
    width: 700px;
    height: 500px;
    border-radius: 10px;
    padding: 20px;
    position: relative;

}
.modalCloseBtn{
    position: absolute;
    top: 10px;
    right: 20px;
    cursor: pointer;
    
    font-size: 26px;
    color:white;
}
.flex{
    display: flex;
    flex-direction: column;
}
.container{
    display: flex;
    justify-content: space-between;
    max-width: 1156px;
    width: 100%;
    margin-top: 79px;
    margin-bottom: 33px;
}
.inputContainer{
    max-width: 563px;
    width: 100%;
    display: flex;
    gap:30px;
    margin-bottom: 16px;
    
}

.title{
    font-size: 41px;
    line-height: 49.2px;
}
.form{
    max-width: 563px;
    width: 100%;
}
.label{
    font-size: 12px;
}
.carInput{
    border:1px solid black;
    width: 100%;
    max-width: 320px;
    height: 40px;
    border-radius: 5px;
    padding-left: 10px;
}
/* .carInput:focus{
    background: red;
} */
.regionContainer{
    margin-left: 30px;
}
.regionInput{
    max-width: 213px;
    width: 100%;
    height: 40px;
    border:1px solid black;
    border-radius: 5px;
    padding-left: 10px;
    
}
.TcInput{
    max-width: 563px;
    width: 100%;
    height: 40px;
    border-radius: 5px;
    border:1px solid black;
    margin-bottom: 16px;
    padding-left: 10px;
}
.btnContainer{
    display: flex;
    gap:21px;
    margin-bottom: 16px;
}
.btnFinesContainer{
    background: #0584FE;
    max-width: 210px;
    width: 100%;
    display: flex;
    height: 45px;
    border-radius: 5px;
    color:white;
    gap:4px;
    align-items: center;
    justify-content: center;
    white-space: nowrap;
}
.btnFinesContainer:hover{
    background: blue
}
.btnFines{
    color:white;
    font-size: 18px;
}

   
.btnServiceContainer{
    max-width: 258px;
    height: 45px;
    width: 100%;
    display: flex;
    gap:4px;
    align-items: center;
    border:1px #0584FE solid;
    border-radius: 5px;
    padding: 0 20px;
}
.btnAboutService{
    white-space: nowrap;
}
.imgContainer{
    max-width: 532px;
    width: 100%;
    }



@media (min-width: 761px) and (max-width: 1200px) {
    .container{
        max-width: 760px;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        gap: 10px;
        margin: 0 auto;
    }
    .inputContainer{
        gap:20px;
    }
    .title{
    font-size: 33px;
}
.imgContainer{
    max-width: 360px;
}
}

@media (min-width: 320px) and (max-width: 760px) {
    .container{
        max-width: 660px;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        gap: 10px;
        margin: 0 auto;
    }
    .inputContainer{
        display: flex;
        padding: 0 20px;
        margin: 0 auto;
        gap:20px;
        max-width: 450px;
    }
    .carInput{
        max-width: 220px;
    }
    .TcInput{
        max-width: 420px;
    }
    .btnContainer{
        gap: 12px;
        padding: 0 10px;
    }
    .btnFines{
        font-size: 16px;
        font-weight: bold;
    }
    
    .btnServiceContainer{
        max-width: 200px;
        padding: 0 5px;
    }
    .title{
    font-size: 33px;
        }
.imgContainer{
    max-width: 360px;
}
}
</style>