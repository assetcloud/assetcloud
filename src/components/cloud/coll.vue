<template>
    <div>
        <div class="banner" id="banner"><img src="../../assets/images/xt-banner.jpg" alt=""></div>
        <div class="text" :style="{height:TxtHeight,minHeight:minH}">
            <p>江省财政厅  浙江省教育厅  浙江省科技厅  杭州电子科技大学  中国美术学院  浙江工商大学  浙江理工大学  浙江师范大学<br />浙江财经大学  中国计量大学  省物品编码中心  用友政务  浙江电信  环保集团  政采云  青云  氚云  中房科技  和轩办公</p>
        </div>
    </div>
</template>
<style scoped>
.banner, .banner img {
    width:100%;
    text-align:center;
}
.text{
    width:70rem;
    margin:0 auto;
    font-size:1.3125rem;
    line-height:2.625rem;
    padding:2rem 0;
}
</style>

<script>
export default {
    data () {
        return {
            TxtHeight:'',
            minH: ''
        }
    },
    methods: {
       init(){
            let that = this
            setTimeout(() => {
                let h = document.getElementById("banner").offsetHeight;
                let zh =184 + h
                let ck = document.documentElement.clientHeight
                that.TxtHeight = (ck - zh) + 'px'
                that.minH = 130 +'px'
               console.log(that.TxtHeight)
            }, 1000);
            window.onresize = function(){
                setTimeout(() => {
                    let h = document.getElementById("banner").offsetHeight;
                    let zh =183 + h
                    let ck = document.documentElement.clientHeight
                    that.TxtHeight = (ck - zh) + 'px'
                    that.minH = 130 +'px'
                console.log(that.TxtHeight)
                }, 1000);
            }
       }

    },
    mounted () {
        this.init();
        
    }
}
</script>
