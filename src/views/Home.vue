<template>
  <div class="home">
    <el-menu  class="el-menu-demo" mode="horizontal" @select="handleSelect">
      <el-menu-item index="1">{{$t('m.home')}}</el-menu-item>
      <el-menu-item index="2">{{$t('m.about')}}</el-menu-item>
      <el-menu-item index="3">{{$t('m.product')}}</el-menu-item>
      <el-menu-item index="4">{{$t('m.contact')}}</el-menu-item>
    </el-menu>
  </div>
</template>

<script>
  // @ is an alias to /src

  export default {
    name: 'Home',
    components: {},
    mounted () {
      this.changeLangEvent()
    },
    methods:{
      /**
       * 切换语言
       */
      changeLangEvent() {
        this.$confirm(this.$t('m.sure_change_lang'), this.$t('m.tips'), {
          confirmButtonText: this.$t('m.sure'),
          cancelButtonText: this.$t('m.cancel'),
          type: 'warning'
        }).then(() => {
          if ( this.lang === 'zh-CN' ) {
            this.lang = 'en-US';
            this.$i18n.locale = this.lang;//关键语句
          }else {
            this.lang = 'zh-CN';
            this.$i18n.locale = this.lang;//关键语句
          }
        }).catch(() => {
          // this.$message({
          //   type: 'info',
          // });
        });
      },
      activeIndex(){},
      handleSelect(){},
    }
  }
</script>
