<template>
    <div class="max-w-[1156px] w-full mb-[85px] flex flex-col justify-center items-center px-3">
        <div class="title">Плюсы использования сервиса Компас для анализа штрафов</div>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-[15px] lg:grid-cols-3 lg:gap-[35px] text-sm">
            <div class="item">
                <div><img src="~/assets/Frame1.png" alt=""></div>
                <div>
                    <h2 class="h2">Неограниченый автопарк</h2>
                    <h4 class="h4">Можно добавить неограниченное кол-во машин и водителей</h4>
                </div>
            </div>
            <div class="item">
                <div><img src="~/assets/Frame2.png" alt=""></div>
                <div>
                    <h2 class="h2">Сокращение затрат до 50%</h2>
                    <h4 class="h4">Максимально быстро узнаете о штрафах в автоматическом режиме, тем самым у вас есть время оплатить по скидке</h4>
                </div>
            </div>
            <div class="item">
                <div><img src="~/assets/Frame3.png" alt=""></div>
                <div>
                    <h2 class="h2">Безопасность</h2>
                    <h4 class="h4">Данные передаются в зашифрованном виде, они доступны только получателю</h4>
                </div>
            </div>
            <div class="item">
                <div><img src="~/assets/Frame4.png" alt=""></div>
                <div>
                    <h2 class="h2">Уведомление о погашении</h2>
                    <h4 class="h4">Мы оповестим вас о том, что штраф был погашен и соответствующая запись создана в ГИС ГМП</h4>
                </div>
            </div>
            <div class="item">
                <div><img src="~/assets/Frame5.png" alt=""></div>
                <div>
                    <h2 class="h2">Квитанция об оплате</h2>
                    <h4 class="h4">После совершения оплаты банковской картой на Вашу электронную почту придет квитанция об успешной оплате.</h4>
                </div>
            </div>
            <div class="item">
                <div><img src="~/assets/Frame6.png" alt=""></div>
                <div>
                    <h2 class="h2">Все история сохраняется по каждой машине</h2>
                    <h4 class="h4">Вся история штрафов сохраняется по машине и водителю, позволяет анализировать статистику по штрафам</h4>
                </div>
            </div>
            
    </div>
    </div>
</template>

<style scoped>
.title{
    display: flex;
    justify-content: center;
    font-size: 34px;
    font-weight: bold;
    margin-bottom: 33px;
}
.item{
    display: flex;
    justify-content: center;
    align-items: center;
    max-width: 362px;
    height: 151px;
    background: #FBFCFD;
    border-radius: 10px;
    border:1px solid #EEEFF1;
    padding: 0 20px;
    gap:15px;
}
.h2{
    color:#1253A2;
    font-size: 18px;
    font-weight: bold;
}
.h4{
    font-size: 15px;
    font-weight: bold;
}
@media screen and (max-width: 760px) {
    .title{
        font-size: 24px;
    }
    .h2{
        font-size: 14px;
    }
    .h4{
        font-size: 12px;
    }
}
</style>