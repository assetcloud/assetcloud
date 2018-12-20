<template>
	<el-container style="height: 100%;">
		<el-header>
      <el-col :span="24" class="panel-top">
        <el-col :span="5">
          <template v-if="logo_type == '1'"></template>
          <template v-else>
            <span class="logoText">{{title}}</span>
          </template>
        </el-col>
        <el-col :span="15">
          <ul class="nav">
            <router-link tag="li" class="li-item" to="/home/index" :class="{'is-active':$route.path === '/home/index'}">首页</router-link>
            <router-link tag="li" class="li-item" to="/home/platform" :class="{'is-active':$route.path === '/home/platform'}">平台服务</router-link>
            <router-link tag="li" class="li-item" to="/home/index">资产云</router-link>
            <router-link tag="li" class="li-item" to="/home/index">资讯动态</router-link>
            <router-link tag="li" class="li-item" to="/home/index">加入协同</router-link>
            <router-link tag="li" class="li-item" to="/home/index">联系我们</router-link>
          </ul>
        </el-col>
        <el-col :span="2">
          <div class="login">
            <span>登录</span>
          </div>
        </el-col>
        <el-col :span="2" class="pos-rel">
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
    <el-container style="height:calc(100% - 130px)">
      <el-main class="panel-c-c-c">
        <router-view v-loading="showLoading"></router-view>
      </el-main>
    </el-container>
    <div class="footer" style="height:70px;">
      <div class="address"><span>中国浙江省杭州杭州市西湖区文一路115号 310012</span></div>
      <div class="phone"><span>联系方式：4008950059</span></div>
      <div class="email">
        <span>邮箱：panzhaohui@msn.com</span>
      </div>
      <div class="copyright"><span>Copyright © 资产云开放协同创新中心</span></div>
    </div>
    <changePwd ref="changePwd"></changePwd>
  </el-container>
</template>
<style>
	.fade-enter-active,
	.fade-leave-active {
		transition: opacity .5s
	}
	.fade-enter,
	.fade-leave-active {
		opacity: 0
	}
	
	.panel {
		position: absolute;
		top: 0px;
		bottom: 0px;
		width: 100%;
	}
	
	.panel-top {
		height: 60px;
		line-height: 60px;
	}
	
	.panel-center {
		background: #324057;
		position: absolute;
		top: 60px;
		bottom: 0px;
		overflow: hidden;
  }
.logoText{
  float: left;
  line-height: 58px;
  font-family: "黑体";
  font-size:1.875rem;
  color: #3d3d3d;
}
.el-menu.el-menu--horizontal{
			border: none;
			display: block;
			float: right;
			height: 40px;
			line-height: 40px;
			padding-top: 9px;
		}
.el-menu--horizontal>.el-menu-item{
			height: 40px;
			line-height: 40px;
			padding: 0;
			margin:0 30px;
		}
.el-menu--horizontal>.el-menu-item a{
			font-size: 20px;
			color: #000;
		}
.el-menu--horizontal>.el-menu-item a:hover, .el-menu--horizontal>.el-menu-item.is-active a{
			color:#f37137;
		}
.el-menu--horizontal>.el-menu-item:hover, .el-menu--horizontal>.el-menu-item.is-active{
			border-bottom: 2px solid #f37137;
    	color:#f37137;
    }
    
.nav {
  display:flex;
  height:40px;
  line-height:40px;
  padding-top:10px;
  margin:0;
}
.nav li {
  margin:0 30px;
  cursor:pointer;
  font-size:1.3125rem;
  padding-bottom:5px;
  border-bottom:2px solid #fff;
}
.nav li.is-active{
  color:#f37137;
  border-bottom:2px solid #f37137;
}
	.login{
    width:128px;
    height:38px;
    border-radius:38px;
    background:#f37137;
    margin-top:11px;
    line-height:38px;
    padding:0 20px;
    box-sizing:border-box;
    background:#f37137 url("../assets/images/login.png") 30px center no-repeat;
    cursor:pointer;
  }
  .login span{
    font-size:20px;
    color:#fff;
    font-family: 'pfb';
    padding-left:40px;
  }
	.panel-c-c {
		background: #f1f2f7;
		right: 0px;
		top: 0px;
		bottom: 0px;
		left: 180px;
		overflow-y: scroll;
		padding: 20px;
	}

  .panel-c-c-c {
    background: #f1f2f7;
  }

	.logout {
		background: url(../assets/images/logout_36.png);
		background-size: contain;
		width: 20px;
		height: 20px;
		float: left;
	}
	
	.logo {
		width: 150px;
		float: left;
		margin: 10px 10px 10px 18px;
	}
	
	.tip-logout {
		float: right;
		margin-right: 20px;
		padding-top: 5px;
		cursor: pointer;
	}
	.pos-rel{
    text-align:right;
    width:80px;
    cursor:pointer;
  }
  .el-dropdown .c-gra{
    color:#2e2e2e
  }
	.admin {
		color: #c0ccda;
		text-align: center;
	}
	.hide-leftMenu {
		left: 0px;
	}
</style>
<script>
  import leftMenu from './Common/leftMenu.vue'
  import changePwd from './Account/changePwd.vue'
  import http from '../assets/js/http'

  export default {
    data() {
      return {
        username: '',
        topMenu: [],
        childMenu: [],
        menuData: [],
        hasChildMenu: false,
        menu: null,
        module: null,
        img: '',
        title: '资产云开放协同创新中心',
        logo_type: null,
        upKey: 1
      }
    },
    methods: {
      logout() {
        this.$confirm('确认退出吗?', '提示', {
          confirmButtonText: '确定',
          cancelButtonText: '取消'
        }).then(() => {
          _g.openGlobalLoading()
          let data = {
            authkey: Lockr.get('authKey'),
            sessionId: Lockr.get('sessionId')
          }
          this.apiPost('admin/base/logout', data).then((res) => {
            _g.closeGlobalLoading()
            this.handelResponse(res, (data) => {
              Lockr.rm('menus')
              Lockr.rm('authKey')
              Lockr.rm('rememberKey')
              Lockr.rm('authList')
              Lockr.rm('userInfo')
              Lockr.rm('sessionId')
              Cookies.remove('rememberPwd')
              _g.toastMsg('success', '退出成功')
              setTimeout(() => {
                router.replace('/')
              }, 1500)
            })
          })
        }).catch(() => {

        })
      },
      switchTopMenu(item) {
        if (!item.child) {
          router.push(item.url)
        } else {
          router.push(item.child[0].child[0].url)
        }
      },
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
      changePwd() {
        this.$refs.changePwd.open()
      },
      getTitleAndLogo() {
        this.apiPost('admin/base/getConfigs').then((res) => {
          this.handelResponse(res, (data) => {
            document.title = data.SYSTEM_NAME
            this.logo_type = data.LOGO_TYPE
            this.title = data.SYSTEM_NAME
            this.img = window.HOST + data.SYSTEM_LOGO
          })
        })
      },
      getUsername() {
        this.username = Lockr.get('userInfo').username
      }
    },
    // created() {
    //   this.getTitleAndLogo()
    //   let authKey = Lockr.get('authKey')
    //   let sessionId = Lockr.get('sessionId')
    //   if (!authKey || !sessionId) {
    //     _g.toastMsg('warning', '您尚未登录')
    //     setTimeout(() => {
    //       router.replace('/')
    //     }, 1500)
    //     return
    //   }
    //   this.getUsername()
    //   let menus = Lockr.get('menus')
    //   this.menu = this.$route.meta.menu
    //   this.module = this.$route.meta.module
    //   this.topMenu = menus
    //   _(menus).forEach((res) => {
    //     if (res.module == this.module) {
    //       this.menuData = res.child
    //       res.selected = true
    //     } else {
    //       res.selected = false
    //     }
    //   })
    // },
    computed: {
      routerShow() {
        return store.state.routerShow
      },
      showLeftMenu() {
        this.hasChildMenu = store.state.showLeftMenu
        return store.state.showLeftMenu
      }
    },
    components: {
      leftMenu,
      changePwd
    },
    watch: {
      '$route' (to, from) {
        _(this.topMenu).forEach((res) => {
          if (res.module == to.meta.module) {
            res.selected = true
            if (!to.meta.hideLeft) {
              this.menu = to.meta.menu
              this.menuData = res.child
            }
          } else {
            res.selected = false
          }
        })
      }
    },
    mixins: [http]
  }
</script>
