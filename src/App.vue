<template lang='pug'>
  v-app
    div.ban
      div.t 載物書院
      div.st Tzai Wu
      div.gp
        v-btn(to='/' text='')
          div.s 關於載物
        v-btn(to='/about' text='')
          div.s 重要公告
        v-btn(to='/search' text='')
          div.s 活動消息
        v-btn(to='/book' text='')
          div.s 空間預約
        v-btn(to='/book' text='')
          div.s 報名載物
    v-content
      router-view
</template>

<script>
export default {
  name: 'App',

  components: {
  },

  data: () => ({
    //
  }),
};
</script>

<style lang="scss" scoped>
@import'assets/scss/main.scss';
.t{
  position: absolute;
  width: 229px;
  height: 53px;
  left: 68px;
  top: 16px;

  font-family: Roboto;
  font-style: normal;
  font-weight: 600;
  font-size: 49px;
  line-height: 57px;
  letter-spacing: 0.1em;
  color: #000000;
}
.st{
  position: absolute;
  width: 126px;
  height: 31px;
  left: 297px;
  top: 38px;
  font-family: Roboto;
  font-style: normal;
  font-weight: normal;
  font-size: 25px;
  line-height: 29px;
  letter-spacing: 0.125em;
  color: #000000;
}
.ban{
  height:91px;
  width:100vw;
  position: fixed;
  z-index: 1000;
  background: white;
}
.gp{
  position: absolute;
  width: 860px;
  height: 31px;
  left: 482px;
  top: 38px;
}
.v-btn{
  position: relative;
  width: 126px;
  height: 31px;
  margin-left: 23px;
  margin-right: 23px;
}
.s{
  font-family: Roboto;
  font-style: normal;
  font-weight: 550;
  font-size: 25px;
  line-height: 29px;
  letter-spacing: 0.28em;
  color: #000000;
}


</style>
