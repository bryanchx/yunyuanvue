<template>
  <div class="home">
    <el-menu class="el-menu-demo" mode="horizontal" @select="handleSelect">
      <el-menu-item index="1">{{$t('m.home')}}</el-menu-item>
      <el-menu-item index="2">{{$t('m.about')}}</el-menu-item>
      <el-menu-item index="3">{{$t('m.product')}}</el-menu-item>
      <el-menu-item index="4">{{$t('m.contact')}}</el-menu-item>
    </el-menu>

    <!--走马灯-->
    <el-carousel :interval="4000" type="card" height="400px" indicator-position="outside">
      <el-carousel-item v-for="item in imagesBox" :key="item.id">
        <img :src="item.idView" class="image">
      </el-carousel-item>
    </el-carousel>
  </div>
</template>

<script>
  // @ is an alias to /src

  export default {
    name: 'Home',
    data () {
      return {
        imagesBox: [
          {
            id: 0,
            idView: require('../../src/assets/images/1.jpg')
          },
          {
            id: 1,
            idView: require('../../src/assets/images/2.jpg')
          },
          {
            id: 2,
            idView: require('../../src/assets/images/3.jpg')
          },
        ],
        fiveNews: []
      }
    },
    components: {},
    mounted () {
      // this.changeLangEvent()
    },
    methods: {
      /**
       * 切换语言
       */
      changeLangEvent () {
        this.$confirm(this.$t('m.sure_change_lang'), this.$t('m.tips'), {
          confirmButtonText: this.$t('m.sure'),
          cancelButtonText: this.$t('m.cancel'),
          type: 'warning'
        }).then(() => {
          if (this.lang === 'zh-CN') {
            this.lang = 'en-US'
            this.$i18n.locale = this.lang//关键语句
          } else {
            this.lang = 'zh-CN'
            this.$i18n.locale = this.lang//关键语句
          }
        }).catch(() => {
          // this.$message({
          //   type: 'info',
          // });
        })
      },
      activeIndex () {
      },
      handleSelect () {
      },
    }
  }
</script>
