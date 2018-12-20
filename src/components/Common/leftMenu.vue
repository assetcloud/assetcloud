<template>
<!-- <div>
<el-menu mode="vertical" default-active="/table" class="el-menu-vertical-demo" @select="handleselect" theme="dark" router>
<el-menu-item-group v-for="menu in menuData" :title="menu.title">
<el-menu-item v-for="item in menu.items" :index="item.path">&nbsp;&nbsp;&nbsp;&nbsp;{{item.name}}</el-menu-item>
</el-menu-item-group>
</el-menu>
</div> -->
  <div>
    <div v-for="(secMenu, index) in menuData" :key="index">
      <div v-if="secMenu.child">
        <el-submenu :index="upKey ? upKey + '-'+ (index+1) : upKey+1">
          <template slot="title">
            <span>{{secMenu.title}}</span>
          </template>
          <leftMenu :menuData="secMenu.child" :upKey="upKey ? upKey + '-'+ (index+1) : upKey+1" ref="leftMenu"></leftMenu>
        </el-submenu>
      </div>
      <div v-else>
        <el-menu-item :index="upKey + '-' + (index+1)" @click="routerChange(secMenu)">{{secMenu.title}}</el-menu-item>
      </div>
    </div>
  </div>
</template>

<script>
  import leftMenu from './leftMenu.vue'
  export default {
    name: 'leftMenu',
    props: ['menuData', 'upKey'],
    data() {
      return {
      }
    },
    methods: {
      routerChange(item) 	{
        // 与当前页面路由相等则刷新页面
        if (item.url != this.$route.path) {
          router.push(item.url)
        } else {
          _g.shallowRefresh(this.$route.name)
        }
      }
    }
  }
</script>