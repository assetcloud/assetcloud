<template>
    <div class="container">
        <div class="banner"><img src="../../assets/images/zcy-banner.jpg" /></div>
        <div class="tab">
            <el-tabs :tab-position="tabPosition">
                <el-tab-pane label="背景意义／Background">
                    <div class="box">
                        <div class="items">
                            <div class="item">
                                <img src="../../assets/images/icon_0.png" alt="">
                                <p class="title">开放性</p>
                                <p>支持第三方全面开放</p>
                            </div>
                            <div class="item">
                                <img src="../../assets/images/icon_1.png" alt="">
                                <p class="title">生态性</p>
                                <p>造政务应用良好生态</p>
                            </div>
                            <div class="item">
                                <img src="../../assets/images/icon_2.png" alt="">
                                <p class="title">平台性</p>
                                <p>提供各类应用开发运维</p>
                            </div>
                        </div>
                        <section>
                            <p>资产云是在贯彻落实<span>创新、协调、绿色、开放、共享</span>的发展理念，加快推进“互联网+政务服务”大背景下，资产管理信息系统整合共享的有力举措，是“数字财政”的重要组成部分。</p>
                            <p>资产云将分散的、独立的资产信息系统整合为一个<span>互联互通、业务协同、信息共享</span>的云服务，可以切实避免资产管理信息系统各自为政、自成体系、重复投资、重复建设。通过对资产云汇集的政府资产大数据的分析和利用，可以提高政府资产配置和使用效益，加快全面规范、公开透明的国有资产报告制度的建立，强化资产管理在财政管理中的基础性作用，支撑政府资产管理的创新需求。</p>
                            <p>资产云平台服务模式推动分散独立的应用向平台间聚合的生态模式转变，促进政府公共资产的有序开放、共享使用，更好的服务于国家治理体系和治理能力的现代化。</p>
                        </section>
                    </div>
                </el-tab-pane>
                <el-tab-pane label="功能特性／Functional ">
                    <div class="box">
                        <div class="items">
                            <div class="item">
                                <img src="../../assets/images/icon_0.png" alt="">
                                <p class="title">开放性</p>
                                <p>支持第三方全面开放</p>
                            </div>
                            <div class="item">
                                <img src="../../assets/images/icon_1.png" alt="">
                                <p class="title">生态性</p>
                                <p>造政务应用良好生态</p>
                            </div>
                            <div class="item">
                                <img src="../../assets/images/icon_2.png" alt="">
                                <p class="title">平台性</p>
                                <p>提供各类应用开发运维</p>
                            </div>
                        </div>
                        <section>
                            <p>资产云是在贯彻落实<span>创新、协调、绿色、开放、共享</span>的发展理念，加快推进“互联网+政务服务”大背景下，资产管理信息系统整合共享的有力举措，是“数字财政”的重要组成部分。</p>
                            <p>资产云将分散的、独立的资产信息系统整合为一个<span>互联互通、业务协同、信息共享</span>的云服务，可以切实避免资产管理信息系统各自为政、自成体系、重复投资、重复建设。通过对资产云汇集的政府资产大数据的分析和利用，可以提高政府资产配置和使用效益，加快全面规范、公开透明的国有资产报告制度的建立，强化资产管理在财政管理中的基础性作用，支撑政府资产管理的创新需求。</p>
                            <p>资产云平台服务模式推动分散独立的应用向平台间聚合的生态模式转变，促进政府公共资产的有序开放、共享使用，更好的服务于国家治理体系和治理能力的现代化。</p>
                        </section>
                    </div>
                </el-tab-pane>
            </el-tabs>
        </div>
    </div>
</template>
<style scoped>
.banner, .banner img{
    width:100%;
}
.tab{
    width:89.375rem;
    margin:0 auto;
    padding-top:4.6875rem;
}
.tab .box{
    padding-left:12.5rem;
    color:#3f3f3f;
}
.tab .box .items{
    display:flex;
}
.tab .box .items .item{
    flex:3;
    text-align:center;
}
.tab .box .items .item img{
    height:4rem;
    width:auto;
}
.tab .box .items .item p{
    margin:0;
    padding:0;
    font-size:1rem;
    line-height:2rem;
    color:#3f3f3f;
}
.tab .box .items .item p.title{
    font-size:1.3125rem;
}
.tab .box section p{
    font-size:1.3125rem;
    line-height:2.625rem;
}
.tab .box section{
    padding-bottom:2rem;
}
.tab .box section p span{
    color:#03a8cb;
}
</style>
<style>
.tab .el-tabs__active-bar{
    display:none;
}
.tab .el-tabs__nav-wrap::after{
    display:none;
}
.tab .el-tabs--left .el-tabs__item.is-left{
    text-align:center;
}
.tab .el-tabs__item{
    text-align:center;
    width:18.4375rem;
    height:2.6875rem;
    line-height:2.6875rem;
    border-radius:2.6875rem;
    background:#c1e2e9;
    color:#000;
    margin-bottom:2.1875rem;
    font-size:1.3125rem;
}
.tab .el-tabs__item.is-active{
    background:#f27036;
    color:#fff;
}
</style>

<script>
export default {
    data() {
      return {
        tabPosition: 'left'
      };
    },
    created() {
        _g.closeGlobalLoading();
    },
}
</script>