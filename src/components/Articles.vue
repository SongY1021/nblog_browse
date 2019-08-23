<template>
  <el-container>
    <el-header class="headerWrapper" height="45px">
      <el-row justify="center" type="flex">
        <el-col :lg="9" :md="12">
          <div class="title-left">
            <a href="javascript:;" class="title-logo">
              <img src="../assets/logo.png" height="45px"/>
            </a>
            <el-menu :default-active="activeIndex" class="el-menu-demo" mode="horizontal" @select="handleSelect">
              <el-menu-item index="1">首页</el-menu-item>
              <el-menu-item index="2">博客</el-menu-item>
              <el-menu-item index="3">热度</el-menu-item>
              <el-menu-item index="4">专题</el-menu-item>
              <el-menu-item index="5">论坛</el-menu-item>
            </el-menu>
          </div>
        </el-col>
        <el-col :lg="9" :md="12">
          <div class="title-right">
            <ul class="toolbar_menu">
              <li class="toolbar_item">
                <el-input placeholder="请输入内容" clearable="true">
                  <i slot="suffix" class="el-input__icon el-icon-search"></i>
                </el-input>
              </li>
              <li class="toolbar_item">
                <a href="javascript:;" class="box_item">
                  <i class="el-icon-edit" style="font-size: 16px;"></i>
                  写博客
                </a>
              </li>
              <li class="toolbar_item">
                <a href="javascript:;" class="box_item">
                  <i class="el-icon-message" style="font-size: 16px;"></i>
                  消息
                </a>
              </li>
              <li class="toolbar_item" v-if="isLogin">
                <a href="javascript:;" class="box_item">
                  <el-avatar icon="el-icon-user-solid" size="small"></el-avatar>
                </a>
              </li>
              <li class="toolbar_item" v-if="!isLogin">
                <a href="javascript:;" class="box_item">
                  登录
                </a>
              </li>
              <li class="toolbar_item" v-if="!isLogin">
                <a href="javascript:;" class="box_item">
                  注册
                </a>
              </li>
            </ul>
          </div>
        </el-col>
      </el-row>
    </el-header>
    <el-main>Main</el-main>
  </el-container>
</template>

<script>
export default {
  data () {
    return {
      activeIndex: '1',
      isLogin: true
    }
  },
  methods: {
    handleSelect (key, keyPath) {
      console.log(key, keyPath)
    }
  }
}
</script>

<style>
  .el-container {
    width: 100%;
    height: 100%;
    position: absolute;
  }
  .el-header {
    /*background-color: #B3C0D1;*/
    color: #333;
    text-align: center;
    line-height: 45px;
    box-shadow: 0 3px 15px 0 rgba(0, 0, 0, 0.15);
  }
  .headerWrapper{
    padding:0;
  }
  .el-main {
    height: 100%;
    /*background-color: #E9EEF3;*/
    color: #333;
    text-align: center;
  }
  .grid-content {
    border-radius: 4px;
    min-height: 45px;
  }
  .bg-purple {
    background: #d3dce6;
  }
  .headerWrapper .el-col{
    height: 45px;
    line-height: 45px;
  }
  .bg-purple-light {
    background: #e5e9f2;
  }
  .headerWrapper a{
    text-decoration: none;
  }
  .headerWrapper .title-logo{
    display: block;
    float: left;

  }
  .headerWrapper .title-left{
    text-align: left;
  }
  .headerWrapper .el-menu.el-menu--horizontal{
    border-bottom: none;
  }
  .headerWrapper .el-menu--horizontal>.el-menu-item{
    height: 45px;
    line-height: 45px;
  }
  .headerWrapper .el-menu-demo {
    height: 45px;
    line-height: 45px;
    display: block;
    float: left;
    margin-left: 20px;
  }
  .headerWrapper .title-right{
    float: right;
  }
  .headerWrapper .toolbar_menu{
    list-style: none;
    position: relative;
    margin: 0;
    padding-left: 0;
    z-index: 20;
  }
  .headerWrapper .toolbar_menu .toolbar_item{
    position: relative;
    float: left;
    height: 45px;
    line-height: 45px;
    margin: 0;
    /*border-top: 2px solid transparent;*/
    color: #909399;
    font-size: 14px;
    /*padding: 0 20px;*/
    cursor: pointer;
    -webkit-transition: border-color .3s,background-color .3s,color .3s;
    -o-transition: border-color .3s,background-color .3s,color .3s;
    transition: border-color .3s,background-color .3s,color .3s;
    -webkit-box-sizing: border-box;
    box-sizing: border-box;
  }
  .headerWrapper .toolbar_menu .toolbar_item .box_item{
    display: inline-block;
    padding: 0 10px;
  }
  .headerWrapper .toolbar_menu .toolbar_item a{
    text-decoration: none;
    /*color: #606266;*/
    color: #909399;
  }
  .headerWrapper .toolbar_menu .toolbar_item a:hover{
    color: #303133;
  }
  .headerWrapper .toolbar_menu .toolbar_item .el-avatar{
    display: inline-table;
  }
  .headerWrapper .toolbar_menu .toolbar_item .el-input__inner{
    height: 30px;
  }
</style>
