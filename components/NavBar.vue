<script setup>

</script>


<template>
    <nav class="navbar">
        <ul>
            <li>
               <NuxtLink to="/"><img src="~/assets/logo.png" alt="logo" class="min-w-[75px]"></NuxtLink>
            
                <NuxtLink to="prices" >Тарифы</NuxtLink>
                <NuxtLink to="contacts" >Контакты</NuxtLink> 
            </li>
                
            <li>
               <div class="phone" >+7 495 118-44-22</div>
                <button class=" hover:bg-blue-400 rounded p-2">Вход</button>
                <button class="btn-register ">Регистрация</button> 
            </li>
                
            
        </ul>
    </nav>
</template>

<style scoped>
.navbar{
    font-size: 18px;
    max-width: 1920px;
    display: flex;
    justify-content: center;
    color:white;
    width: 100%;
    height: 60px;
    background:  linear-gradient(90deg, #000000 30%, #1C2734 73%);
}
.navbar ul{
    max-width: 1156px;
    display: flex;
    width: 100%;
    align-items: center;
    justify-content: space-between;
      
}
.navbar ul li{
    display: flex;
    align-items: center;
    gap: 30px;
}

.phone{
    white-space: nowrap;
}
.btn-register{
   background: #0584FE;
   max-width: 117px;
   width: 100%;
   height: 37px;
   font-size: 15px;
   border-radius: 8px;
   padding: 0 18px;
}
.btn-register:hover{
    background: #065ea7;
}


@media (min-width: 761px) and (max-width: 1500px) {
    .navbar{
        font-size: 14px;
    }
    .navbar ul{
        margin: 0 150px;
        
    }
    .navbar ul li{
        display: flex;
    gap: 20px;
}
    .phone{
        font-size: 12px;
    }
}

@media (min-width: 380px) and (max-width: 760px) {
    .navbar{
        font-size: 12px;
        height: 100px;
        padding:10px 10px;
    }
    .navbar ul{
        margin: 0 80px;
        display: flex;
        flex-direction: column;
        gap: 10px;
    }
    .navbar ul li{
        display: flex;
    gap: 10px;
    }
    .phone{
        font-size: 20px;
    }
}
</style>