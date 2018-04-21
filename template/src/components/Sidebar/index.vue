<template>
  <div id="sidebar" :class="{'open': aactive}">
    <el-menu theme="light" router>
      <el-menu-item class="header-navicon" index="9">
        <el-button type="text" @click="closeSidebar">
          <i class="md-icon">close</i>
        </el-button>
      </el-menu-item>
      <div class="logo-container">
        <img class="logo" src="https://vuejs.org/images/logo.png" />
      </div>
      <el-menu-item index="/">Dashboard</el-menu-item>
      <el-submenu index="1">
      <template slot="title">
          Categories
      </template>
      <el-menu-item-group title="JS Posts">
        <el-menu-item index="/post/1">Post #1</el-menu-item>
        <el-menu-item index="/post/2">Post #2</el-menu-item>
      </el-menu-item-group>
      <el-menu-item-group title="Python Posts">
        <el-menu-item index="/post/3">Post #3</el-menu-item>
      </el-menu-item-group>
      <el-submenu index="1-4">
        <template slot="title">Archived Posts</template>
        <el-menu-item index="/post/4">Post #4</el-menu-item>
      </el-submenu>
      </el-submenu>
      <el-menu-item index="/about">About</el-menu-item>
    </el-menu>
  </div>
</template>

<script>
export default {
  name: 'Sidebar',
  props: ['active','closeSidebar'],
  computed: {
    aactive () {
      console.log(this)
      return this.active
    }
  }
}
</script>

<style lang="scss">
// You can import all your SCSS variables using webpack alias
@import '../../../src/styles/vars.scss';
// @import '~scss_vars';
@import './style.scss';
</style>
