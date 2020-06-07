<template>
  <div class="home">
    <el-menu :default-active="activeIndex" class="el-menu-demo" mode="horizontal" @select="handleSelect">
      <el-menu-item index="1">首页</el-menu-item>
    </el-menu>
  </div>
</template>

<script>
  // @ is an alias to /src

  export default {
    name: 'Home',
    components: {}
  }
</script>
