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
                <el-input placeholder="请输入内容" clearable v-model="keywords">
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
    <el-main>
      <el-row justify="center" type="flex" :gutter="10">
        <el-col :lg="2" :md="3" :sm="3" :xs="3">
          <div class="content-menu">
            <ul class="toolbar_menu">
              <li class="toolbar_item active">
                <a href="javascript:;" class="box_item">
                  推荐
                </a>
              </li>
              <li class="toolbar_item">
                <a href="javascript:;" class="box_item">
                  关注
                </a>
              </li>
              <li class="toolbar_item">
                <a href="javascript:;" class="box_item">
                  Java
                </a>
              </li>
              <li class="toolbar_item">
                <a href="javascript:;" class="box_item">
                  Python
                </a>
              </li>
              <li class="toolbar_item">
                <a href="javascript:;" class="box_item">
                  C/C++
                </a>
              </li>
              <li class="toolbar_item">
                <a href="javascript:;" class="box_item">
                  前端
                </a>
              </li>
              <li class="toolbar_item">
                <a href="javascript:;" class="box_item">
                  架构
                </a>
              </li>
              <li class="toolbar_item">
                <a href="javascript:;" class="box_item">
                  区块链
                </a>
              </li>
              <li class="toolbar_item">
                <a href="javascript:;" class="box_item">
                  数据库
                </a>
              </li>
              <li class="toolbar_item">
                <a href="javascript:;" class="box_item">
                  人工智能
                </a>
              </li>
              <li class="toolbar_item">
                <a href="javascript:;" class="box_item">
                  云计算/大数据
                </a>
              </li>
            </ul>
          </div>
        </el-col>
        <el-col :lg="11" :md="16" :sm="16" :xs="16">
          <div class="content">
            <el-row class="content-banner" :gutter="2">
              <el-col :span="16" class="content-banner-col">
                <div class="banner">
                  <el-carousel :interval="5000" arrow="hover" height="304px">
                    <el-carousel-item v-for="item in 4" :key="item">
                      <h3>{{ item }}</h3>
                    </el-carousel-item>
                  </el-carousel>
                </div>
              </el-col>
              <el-col :span="8">
                <el-row>
                  <el-col :span="24" class="content-banner-right">
                    <el-image :src="src1">
                      <div slot="placeholder" class="image-slot">
                        加载中<span class="dot">...</span>
                      </div>
                    </el-image>
                  </el-col>
                  <el-col :span="24" class="content-banner-right">
                    <el-image :src="src2">
                      <div slot="placeholder" class="image-slot">
                        加载中<span class="dot">...</span>
                      </div>
                    </el-image>
                  </el-col>
                </el-row>
              </el-col>
            </el-row>
            <el-alert title="您有新的推荐内容，请点击查看" type="error" effect="dark"></el-alert>
          </div>
        </el-col>
        <el-col :lg="5" :md="5" :sm="5" :xs="5">
          <div class="content-bar">
            <div class="tip">今日推荐</div>
          </div>
        </el-col>
      </el-row>
    </el-main>
  </el-container>
</template>

<script>
export default {
  data () {
    return {
      activeIndex: '1',
      isLogin: true,
      keywords: '',
      src1: 'https://cube.elemecdn.com/6/94/4d3ea53c084bad6931a56d5158a48jpeg.jpeg',
      src2: 'https://csdnimg.cn/feed/20190822/38b4e488f6082aa4f71596cc04cd49d6.png'
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
    min-width: 1190px;
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
    min-width: 1190px;
    color: #333;
    text-align: center;
    padding: 20px 10px 0;
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
    margin-left: 10px;
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
  .el-main .el-row {
    height: 100%;
  }
  .el-main .content-menu{
    position: relative;
    height: 100%;
  }
  .content-menu .toolbar_menu{
    list-style: none;
    position: absolute;
    width: 100%;
    top: 0;
    margin: 0;
    padding-left: 0;
    z-index: 20;
  }
  .content-menu .toolbar_menu .toolbar_item{
    position: relative;
    height: 40px;
    line-height: 40px;
    width: 100%;
    border-bottom: #FFF solid 1px;
    border-radius: 4px;
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
  .content-menu .toolbar_menu .toolbar_item .box_item{
    display: inline-block;
    padding: 0 10px;
  }
  .content-menu .toolbar_menu .toolbar_item a{
    text-decoration: none;
    color: #606266;
  }
  .content-menu .toolbar_menu li:hover a,.content-menu .toolbar_menu .active a{
    color: #FFFFFF;
  }
  .content-menu .toolbar_menu li:hover, .content-menu .toolbar_menu .active{
    color: #FFFFFF;
    background-color: #409EFF;
  }
  .el-main .content{
    height: 100%;
  }
  .content .content-banner{
    height: 304px;
  }
  .content .content-banner .content-banner-col{
    height: 100%;
  }
  .content .content-banner .banner{
    height: 100%;
  }
  .content .el-carousel__item h3 {
    padding: 2px 0;
    color: #475669;
    font-size: 18px;
    opacity: 0.75;
    line-height: 300px;
    margin: 0;
  }

  .content .el-carousel__item:nth-child(2n) {
    background-color: #99a9bf;
  }
  .content .el-carousel__item:nth-child(2n+1) {
    background-color: #d3dce6;
  }
  .content .el-image{
    width: 100%;
    height: 150px;
    background-color: #409EFF;
  }
  .content .content-banner-right{
    padding: 1px;
    height: 152px;
  }
  .content .content-remind {
    margin-top: 15px;
  }
  .content .el-alert {
    margin-top: 15px;
  }
  .el-main .content-bar{
    height: 100%;
    /*min-width: 300px;*/
  }
  .content-bar .tip {
    /*padding: 0.5px 4px;*/
    height: 40px;
    line-height: 40px;
    font-size: 15px;
    background-color: #ecf8ff;
    border-radius: 4px;
    border-left: 5px solid #409EFF;
  }
</style>
