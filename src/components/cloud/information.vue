<template>
    <div class="container">
        <div class="banner"><img src="../../assets/images/information.jpg" alt=""></div>
        <div class="qh">
            <el-carousel :interval="10000" indicator-position="outside">
                <el-carousel-item v-for="item in 4" :key="item">
                    <div class="box">
                        <div class="item">
                            <img src="../../assets/images/new1.png" alt="">
                            <p class="title">资产云开发协同中心正式成立</p>
                            <p class="date">2018年9月1日</p>
                            <p class="text">资产云开放协同创新中心正式成立，中心具体负责“资产云”落地示范以及全省推广。</p>
                        </div>
                        <div class="item">
                            <img src="../../assets/images/new2.png" alt="">
                            <p class="title">资产云物联网协同项目</p>
                            <p class="date">2018年9月1日</p>
                            <p class="text">杭州电子科技大学资产云落地示范，利用物联网技术提高资产绩效项目取得阶段成果。</p>
                        </div>
                        <div class="item">
                            <img src="../../assets/images/new3.png" alt="">
                            <p class="title">国有资产管理云服务平台上线</p>
                            <p class="date">2018年1月1日</p>
                            <p class="text">2018年1月政府国有资产管理云服务平台正式上线运行</p>
                        </div>
                    </div>
                </el-carousel-item>
            </el-carousel>
        </div>
    </div>
</template>
<style scoped>
.banner, .banner img{
    width:100%;
}
.qh{
    padding-top: 8.125rem;
    min-height:659px;
    background: #f0f0f0;
}
.box {
    width:99.125rem;
    margin:0 auto;
    display:flex;
    justify-content: center;
}
.box .item{
    width:31.5rem;
    border-radius:0.375rem;
    background:#fff;
    margin-left:2.5rem;
}
.box .item img{
    width:100%;
    height:auto;
}
.box .item p{
    padding: 0 2.5rem;
}
.box .item p.title{
    font-size:1.75rem;
}
.box .item p.date{
    font-size:1.3125rem;
    color:#878787;
}
.box .item p.text{
    font-size:1.3125rem;
    color:#000;
    padding-top:3.3125rem;
    margin-top:0;
    line-height:2.625rem;
}
.box .item:first-child{
    margin-left:0;
}
</style>
<style>
.qh .el-carousel__container{
    height:35rem;
}
</style>


<script>
export default {
    
}
</script>

