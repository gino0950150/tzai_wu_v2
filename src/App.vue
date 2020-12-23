<template>
  <v-app>
    <v-card
      app
      color='white'
      tile
      height="9vh"
      class="d-flex align-center"
    >
      <v-col  cols='4'>
        <span class="title text-h4" color='primary'>載物書院<span class="text-h6" color='primary'> Tzai Wu</span></span>
      </v-col>
      <v-col 
        cols="4"
        class="d-flex justify-center">
        <v-btn to="/" text>
          <span class="text-h6">關於載物</span>
        </v-btn>
        <v-btn to="/about" text>
          <span class="text-h6">重要公告</span>
        </v-btn>
        <v-btn to="/search" text>
          <span class="text-h6">活動消息</span>
        </v-btn>
        <v-btn to="/book" text>
          <span class="text-h6">空間預約</span>
        </v-btn>   
      </v-col>
    </v-card>

    <v-content>
      <router-view />
    </v-content>
  </v-app>
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
.title{
  position: relative;
  left:5vw;
}
.v-btn:hover { 
  background-color: rgba(201, 201, 201, 0.294);
}
.v-btn--active {
  color:$secondColor !important;
  background: rgb(255, 255, 255) !important;
}
.v-btn::before{
  background: rgb(255, 255, 255) !important;
}
.v-btn::after{
  background: rgb(255, 255, 255) !important;
}
.v-ripple__container {
    display:none !important;
}

</style>
