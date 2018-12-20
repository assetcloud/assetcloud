<template>
    <div class="content">
        <el-carousel indicator-position="outside">
            <el-carousel-item v-for="item in imgs" :key="item.id">
                <div class="banner" :style="{backgroundImage: 'url(' + item.url + ')'}">
                    <div class="left">
                        <h3>{{item.title}}</h3>
                        <h4>{{item.h}}</h4>
                        <p v-html="item.text">{{item.text}}</p>
                        <p class="fg">我们是开放的组织，<br />我们欢迎所有富有创意和激情的团队的加入！</p>
                        <button>加入协同</button>
                    </div>
                </div>
            </el-carousel-item>
        </el-carousel>
        <div class="platform">
            <el-row>
              <el-col :span="6"><div class="item item1">协同平台</div></el-col>
              <el-col :span="6"><div class="item item2">应用平台</div></el-col>
              <el-col :span="6"><div class="item item3">创新平台</div></el-col>
              <el-col :span="6"><div class="item item4">共享平台</div></el-col>
            </el-row>
        </div>
    </div>
</template>

<style>
.content{
    height:calc(100vh - 130px);
    min-height:659px;
    position:relative;
}
.el-carousel__container{
    height:calc(100vh - 130px);
    min-height:659px;
    background: #0071be;
}
.el-carousel__container .banner{
    width:100%;
    height:100%;
    background-position: right 100px;
    background-size:700px;
    background-repeat: no-repeat;
}
.el-carousel__container .banner .left{
    float: left;
    margin-left: 200px;
    color: #fff;
    padding-top:100px;
    font-family: 'pfb';
}
.el-carousel__container .banner .left h3, .el-carousel__container .banner .left h4{
    font-size:3.75rem;
    margin:0;
}
.el-carousel__container .banner .left h4{
    font-size:30px;
}
.el-carousel__container .banner .left p{
    font-size:1.3125rem;
    line-height:2.625rem;
}
.el-carousel__container .banner .left p.fg{
    padding-top:2rem;
}
.el-carousel__container .banner .left button{
    background-color:transparent;
    border:none;
    border-radius:4rem;
    width:14.25rem;
    height:4rem;
    color:#fff;
    text-align: center;
    line-height:4rem;
    background:#f26222;
    cursor:pointer;
    outline:none;
    font-size:1.5rem;
    letter-spacing:2;
}
.el-carousel__container .banner .right{
    float:right;
}
.el-carousel__container .banner .right img{
    width:50%;
}
.el-carousel__indicators{
    position: absolute;
}
.el-carousel__indicator button, .el-carousel__indicator:hover button, .el-carousel__indicator.is-active button{
    background-color: transparent;
}
.platform{
    position: absolute;
    width:81.9375rem;
    height:12.5rem;
    left:50%;
    margin-left:-500px;
    bottom:1rem;
    background:url('../../assets/images/pt-bg.png') left bottom no-repeat;
    background-size:81.9375rem 7.5rem;
    z-index:999999;
    padding:0 4.375rem 0 3.75rem;
    text-align:center;
    box-sizing:border-box;
}
.platform .item{
    padding-top:8.75rem;
    cursor:pointer;
}
.platform .item:hover{
    background-size:10.125rem;
}
.platform .item1{
    background:url('../../assets/images/icon1.png') center top no-repeat;
    background-size:8.75rem auto;
}
.platform .item2{
    background:url('../../assets/images/icon2.png') center top no-repeat;
    background-size:8.75rem auto;
}
.platform .item3{
    background:url('../../assets/images/icon3.png') center top no-repeat;
    background-size:8.75rem auto;
}
.platform .item4{
    background:url('../../assets/images/icon4.png') center top no-repeat;
    background-size:8.75rem auto;
}
</style>


<script>
export default {
    data () {
        return {
            activeIndex: '1',
            imgs:[
                {	
                    id:0,
                    url: require('../../assets/images/banner1.png'),
                    title: 'ASSET CLOUD',
                    h: '资产云开放协同创新中心',
                    text: '促进政务软件从分散独立的应用向平台间聚合的生态模式转变，<br />为全社会数字化转型探索有效路径。'
                },
                {
                    id:1,
                    url:require('../../assets/images/banner2.png'),
                    title: '协同平台',
                    text:'为开发者提供标准应用开发框架与工具，<br />支撑应用快速开发和上线，协同单位之间<br />开放共享公共组件，提高运维效率。'
                },
                {	
                    id:2,
                    url: require('../../assets/images/banner3.png'),
                    title:'应用管理平台',
                    text: '提供主流微服务框架的支持，广泛兼容主流开源应用<br />研发生态，帮助企业快速构建基于容器、<br />微服务、DevOps的开发体验，<br />帮助开发商全面拥抱云服务趋势。'
                },
                {	
                    id:3,
                    url: require('../../assets/images/banner4.png'),
                    title:'创新平台',
                    text: '通过开放、协同、共建、共享模式推动各领域创新<br />整合各类资源的基础上，搭建一个公共的创新平台。'
                },
                {	
                    id:4,
                    url: require('../../assets/images/banner5.png'),
                    title:'共享平台',
                    text: '为仪器共享 场馆共享 办公空间共享 图书共享<br /> 科技成果共享 信息共享 数据共享 <br />等各类资产资源共享提供平台、工具和服务支持。'
                }
            ]
        }
    },
    created() {
        _g.closeGlobalLoading();
    },
}
</script>
