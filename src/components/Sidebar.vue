<template>
  <div id="Sidebar" class="theme-success light-skin">

    <aside class="main-sidebar">
      <!-- sidebar-->
      <section class="sidebar">

        <div class="user-profile">
          <div class="ulogo">
            <!-- logo for regular state and mobile devices -->
            <div class="d-flex align-items-center justify-content-center">
              <!--<img src="./../assets/images/logo.png" alt="" height="40" width="40" style="margin-right: 20px">-->
              <h4><b>第二课堂</b></h4>
            </div>
          </div>
        </div>

        <!-- sidebar menu-->

        <el-row class="tac">
          <el-col :span="12">
            <el-menu
              :default-active="$route.path"
              router
              class="sidebar-menu el-menu-vertical-demo"
              style="width: 260px"
              background-color="#ffffff"
              text-color="#919ebc"
              active-text-color="#1bc5bd"
              @open="handleOpen"
              @close="handleClose">
              <el-menu-item index="/overallview">
                <i class="feather" data-feather="grid" style="color:#919ebc;margin-right: 10px; "/>
                <span style="font-size:14px">预警与总览</span>
              </el-menu-item>
              <el-submenu index="1">
                <template slot="title">
                  <i class="feather" data-feather="pie-chart" style="color:#919ebc;background-color:#f7f8f8;border-radius: 12px;margin-right: 10px; "/>
                  <span>活动模块</span>
                </template>
                <el-menu-item index="/activityinquiry"><i class="fa fa-ellipsis-h" style="color:#919ebc"/>活动查询与创建</el-menu-item>
                <el-menu-item index="/activityapproval"><i class="fa fa-ellipsis-h" style="color:#919ebc"/>活动审批</el-menu-item>
                <el-menu-item index="/authorization"><i class="fa fa-ellipsis-h" style="color:#919ebc"/>权限分配</el-menu-item>
              </el-submenu>
              <el-submenu index="2">
                <template slot="title">
                  <i class="feather" data-feather="message-circle" style="color:#919ebc;background-color:#f7f8f8;border-radius: 11px;margin-right: 10px; "/>
                  <span>活动章模块</span>
                </template>
                <el-menu-item index="/activitychapter"><i class="fa fa-ellipsis-h" style="color:#919ebc"/>导入章</el-menu-item>
                <el-menu-item index="/chapterinout"><i class="fa fa-ellipsis-h" style="color:#919ebc"/>导入/导出章</el-menu-item>
              </el-submenu>
              <el-submenu index="3">
                <template slot="title">
                  <i class="feather" data-feather="mail" style="color:#919ebc;background-color:#f7f8f8;border-radius: 5px;margin-right: 10px; "/>
                  <span>帐号模块</span>
                </template>
                <el-menu-item index="/informationentry"><i class="fa fa-ellipsis-h" style="color:#919ebc"/>新生信息录入</el-menu-item>
              </el-submenu>
            </el-menu>
          </el-col>
        </el-row>
      </section>
    </aside>

  </div>
</template>

<script>
export default {
  name: 'Sidebar',
  data() {
    return {
    }
  },
  methods: {
    tologin() {
      const _this = this
      // request.$post('/user/logout', {}, (res) => {
      //   console.log(res.data);
      //   request.localStorageSet('token', null);
      setTimeout(function() {
        _this.$router.push('/signin')
        // location.reload();
      }, 3000)
      // let message = res.data.message;
      // }, _this)
    },
    handleOpen(key, keyPath) {
      console.log(key, keyPath)
    },
    handleClose(key, keyPath) {
      console.log(key, keyPath)
    }
  }
}
</script>

<style scoped>
.el-menu-vertical-demo:not(.el-menu--collapse) {
    width: 200px;
    min-height: 400px;
  }
.el-menu {
  border-right: 0ch !important;
}
.el-menu-item{
  font-size: 13px;
}
.el-menu-item i.fa-ellipsis-h{
  margin-right: 10px;
}
.el-menu-item.is-active i.fa-ellipsis-h:before{
  content: "\f178";
  color: #475f7b;
}
.el-menu-item:hover i.fa-ellipsis-h:before{
  content: "\f178";
  color: #475f7b;
}
.el-menu-item.is-active {
  background-color:  rgba(27, 197, 189, 0.2) !important;
  color: #475f7b !important;
}
.el-menu-item-group .el-menu-item.demo:hover{
  background: #ffffff !important;
  color: #fff !important;
}
.el-menu-item:hover {
  background-color: #fff !important;
  color: #475f7b !important;
}
</style>

<style lang="less">
.el-submenu:hover .feather{
  background-color: #ffffff !important;
  color: #475f7b !important;
  i {
    color: #475f7b !important;
  }
}
.el-submenu .el-submenu__title:hover{
  background-color: #ffffff !important;
  color: #475f7b !important;
  i {
    color: #475f7b !important;
  }
}
</style>
