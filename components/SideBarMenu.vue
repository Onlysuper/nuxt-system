<template>

  <el-menu default-active="1-4-1" class="el-menu-vertical-demo" :collapse="isCollapse" :fit="true" :unique-opened="true">
    <el-submenu v-for="(item) of menuData.data" :index="item.menuCode" :key="item.menuCode">
      <template slot="title">
        <i class="el-icon-location"></i>
        <span slot="title">{{item.menuName}}</span>
      </template>
     
      <el-menu-item-group v-for="(child) of item.child" :index="child.menuCode" :key="child.menuCode">
        <el-menu-item :index="child.menuCode">{{child.menuName}}</el-menu-item>
      </el-menu-item-group>
    </el-submenu>
  </el-menu>
</template>

<style>
</style>
<script>
export default {
  props:["isCollapse","menuData"],
  methods:{
    handleOpen(key, keyPath) {
        console.log(key, keyPath);
      },
      handleClose(key, keyPath) {
        console.log(key, keyPath);
      }
  }
}
</script>
