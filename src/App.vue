<template>
	<div id="app" class="is-component">
		<el-header>
			<el-col :span="24" class="panel-top">
				<el-col :span="5" :lg="4" :md="4">
				<template v-if="logo_type == '1'"></template>
				<template v-else>
					<span class="logoText">资产云开放协同创新中心</span>
				</template>
				</el-col>
				<el-col :span="15" :lg="15" :md="15">
				<ul class="nav">
					<router-link tag="li" class="li-item" to="/" :class="{'is-active':$route.path === '/'}">首页</router-link>
					<router-link tag="li" class="li-item" to="/platform" :class="{'is-active':$route.path === '/platform'}">平台服务</router-link>
					<router-link tag="li" class="li-item" to="/cloud" :class="{'is-active':$route.path === '/cloud'}">资产云</router-link>
					<router-link tag="li" class="li-item" to="/information" :class="{'is-active':$route.path === '/information'}">资讯动态</router-link>
					<router-link tag="li" class="li-item" to="/coll" :class="{'is-active':$route.path === '/coll'}">加入协同</router-link>
					<!-- <router-link tag="li" class="li-item" to="/home/index">联系我们</router-link> -->
				</ul>
				</el-col>
				<el-col :span="2" :lg="2" style="width:128px">
				<div class="login" @click="login()">
					<span>登录</span>
				</div>
				</el-col>
				<el-col :span="2" :lg="2" class="pos-rel">
				<el-dropdown @command="handleMenu" class="user-menu p-r-5">
					<span class="el-dropdown-link c-gra" style="cursor: default">
					中文&nbsp;<i class="el-icon-arrow-down"></i>
					</span>
					<el-dropdown-menu slot="dropdown">
					<el-dropdown-item>英文</el-dropdown-item>
					</el-dropdown-menu>
				</el-dropdown>
				</el-col>
			</el-col>
		</el-header>

		<div v-show="isShow" class="loginbox">
			<div class="login-H">
				<div class="pw">密码登录</div>
				<div class="sm"></div>
			</div>
			<el-form ref="form" :model="form">
				<el-form-item>
					<el-input v-model="form.name" placeholder="邮箱／会员名／ID账号"></el-input>
				</el-form-item>
				<el-form-item>
					<el-input type="password" v-model="form.password" placeholder="请输入登录密码"></el-input>
				</el-form-item>
				<el-form-item>
					<el-button style="width:100%;" type="primary" @click="onSubmit">登录</el-button>
				</el-form-item>
			</el-form>
			<div class="wj"><a href="#">忘记密码</a><a href="#">忘记会员名</a><a href="#">免费登录</a></div>
			<div class="other-login"><span>其他方式登录：</span><a href="#" class="tb"></a><a class="yl" href="#"></a><a class="sina" href="#"></a><a class="zfb" href="#"></a><a class="dd" href="#"></a></div>
		</div>

		<transition name="bounce">
			<router-view></router-view>
		</transition>

		<div class="footer" style="height:70px;">
			<div class="address"><span>中国浙江省杭州杭州市西湖区文一路115号 310012</span></div>
			<div class="phone"><span>联系方式：4008950059</span></div>
			<div class="email">
				<span>邮箱：panzhaohui@msn.com</span>
			</div>
			<div class="copyright"><span>Copyright © 资产云开放协同创新中心</span></div>
		</div>
	</div>
</template>

<script>
export default {
  name: 'app',
  data () {
	  return {
		form: {
          name: '',
          password:''
		},
		isShow:false
	  }
  },
  methods: {
	handleMenu(val) {
        switch (val) {
          case 'logout':
            this.logout()
            break
          case 'changePwd':
            this.changePwd()
            break
        }
	}, 
	login(){
		this.isShow = !this.isShow
	},
	 onSubmit() {
		 this.isShow = !this.isShow
        console.log('submit!');
      }
  },
  components: {
  }
}
</script>

<style>
	@import "assets/css/font-awesome.min.css";
	.bounce-enter-active {
		animation: bounce-in .5s;
	}

	.bounce-leave-active {
		animation: bounce-out .2s;
	}

	@keyframes bounce-in {
		0% {
			transform: scale(0);
		}
		50% {
			transform: scale(1.05);
		}
		100% {
			transform: scale(1);
		}
	}

	@keyframes bounce-out {
		0% {
			transform: scale(1);
		}
		50% {
			transform: scale(0.95);
		}
		100% {
			transform: scale(0);
		}
	}
	body {
		margin: 0px;
		padding: 0px;
		background: #1F2D3D;
		font-family: Helvetica Neue, Helvetica, PingFang SC, Hiragino Sans GB, Microsoft YaHei, SimSun, sans-serif;
		font-weight: 400;
		-webkit-font-smoothing: antialiased;
	}
	#app {
		position: absolute;
		top: 0px;
		bottom: 0px;
		width: 100%;
	}
	/* #app.is-component {
		overflow-y: hidden;
	} */

	.el-submenu [class^=fa] {
		vertical-align: baseline;
		margin-right: 10px;
	}

	.el-menu-item [class^=fa] {
		vertical-align: baseline;
		margin-right: 10px;
	}
</style>