<template>
  <div class="container">
    <div class="row">
        <div class="col-lg-6 txtWrap p-3">
            <h2>채용공고</h2>
            <p>변화를 두려워하지 않는 열정과 창의적인 사고로 <br> 함께 소통하고 발전하는 인재를 찾습니다.</p>
        </div>
        <div class="col-lg-6 iconWrap gap-5">
            <a href="#!"><img :src="`./images/05RecruitView/05-01.png`" alt=""></a>
            <a href="#!"><img :src="`./images/05RecruitView/05-02.png`" alt=""></a>
            <a href="#!"><img :src="`./images/05RecruitView/05-03.png`" alt=""></a>
            <a href="#!"><img :src="`./images/05RecruitView/05-04.png`" alt=""></a>
        </div>
    </div>
    <div class="reWrap">
        <div class="txWrap p-3">
            <div class="tWrap after p-5" v-for="(item,i) in 4" :key="i">
               
                <div>
                    <h3 class="mb-4">{{rData[i].title}}</h3>
                    <div class="dateWrap">
                        <p style="color:red">{{rData[i].date}}</p><span></span>
                        <p>{{rData[i].target}}</p><span></span>
                        <p>{{rData[i].name}}</p>
                    </div>
                </div>
            </div>
        </div>
        <div class="img img-fluid"><img :src="`/images/05RecruitView/05img.png`" alt=""></div>
    </div>
    
  </div>
</template>

<script>
import rData from "@/data/05RecruitView.js"

export default {
    setup(){
        return{
            rData:rData,
        }
    }

}

</script>

<style lang="scss" scoped>
.txtWrap{
    h2{font-size: 50px;}
    p{font-size: 22px;}
}
.iconWrap{
    display: flex;justify-content: center;align-items: center;
    gap: 5px;
    img{width: 100px;}
}
.reWrap{
    width: 100%;height: 730px;
    display: flex;

.txWrap{
    width: calc(150% / 2);
    height: 100%;
   
    .tWrap{
        height: calc(100%/4);
        display: flex;flex-direction: column;
        font-size: 24px;
        margin-bottom: 5px;
        .dateWrap{
            display: flex; align-items: center;
            p{font-size: 14px;}
            span{display: flex; justify-content: center; align-items: center;
                margin: 0 10px; width: 2px;height: 18px; background: #CDD0D2;}
        }
        &.after{display: block; border-bottom: 1px solid #DCDDDE;}
    }
    
}
.img{
    position: absolute;
    right: 0;
}
}


</style>