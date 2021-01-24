<template lang='pug'>
#Home
  img.frame(v-bind:src='mainImage')
  v-hover
    #f3(v-on:click="link")
      .ifm
      .t1 【移工人生體驗桌遊，最後一場！】
      .t2  我們想要別人怎麼對待台灣人 要先從友善的對待移工開始。
  vue-horizontal-list.acontainer(:items='items' :options='options')
    template(v-slot:default='{ item }')
      .image-container(v-on:mouseover="mainImage = item.image")
        img(:src='item.image')
  .div.intro 書院介紹
  .div.line 
  flipbook.flipbook(v-bind:pages="pages", singlePage = true, canZoomIn = 0, canZoomOut = 0)
  .prompt ⇣翻頁
  iframe.vid(width='670' height='430' src='https://www.youtube.com/embed/7yS0Y-nI_L0' frameborder='0' allow='accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture' allowfullscreen='')
</template>
<script>
// @ is an alias to /src
import Flipbook from 'flipbook-vue';
import VueHorizontalList from "vue-horizontal-list";
export default {
  name: 'Home',
  data() {
    return {
      pages: [null,require("../assets/pics/ppt/1.png"),
            require("../assets/pics/ppt/2.png"),
            require("../assets/pics/ppt/3.png"),
            require("../assets/pics/ppt/4.png"),
            require("../assets/pics/ppt/5.png"),
            require("../assets/pics/ppt/6.png")],
      da:require('@/assets/pics/4.png'),
      mainImage: require('@/assets/pics/3.png'), 
      items: [
        {
          image: require('@/assets/pics/4.png'),
        },
        {
          image: require('@/assets/pics/7.jpg'),
        },
        {
          image: require('@/assets/pics/8.jpg'),
        },
        {
          image: require('@/assets/pics/2.png'),
        },
        {
          image: require('@/assets/pics/6.jpg'),
        },
        {
          image: require('@/assets/pics/3.png'),
        },
      ],
      options: {
        responsive: [
          { end: 576, size: 3 },
          { start: 576, end: 768, size: 3 },
          { size: 6 },
        ],
      },
    }
  },
  components: { Flipbook, VueHorizontalList},
  methods: {
    link: function () {
      window.open("https://www.facebook.com/MigrantWorkersFriendlyUnion/posts/205754137881470")
    }
  }
}
</script>
<style lang='scss'>
@import url(https://fonts.googleapis.com/css?family=Raleway);
@import'../assets/scss/main.scss';
.frame {
  position: absolute;
  width: 745px;
  height: 457px;
  left: 0px;
  top: 0px;
  background-color: #eee;
  background-position: center;
  background-size: cover;
}

#Home{
  position: absolute;
  width: 1370px;
  height: 1021px;
  left: 68px;
  top: 91px;
}
.flipbook {
  position: absolute;
  width: 571.6px;
  height: 444.64px;
  left:0px;
  top :580px; 
}
#f3{
  position: absolute;
  width: 573px;
  height: 307px;
  left: 799px;
  background: #FFFFFF;
  border: 4px solid #E1E1E1;
  box-sizing: border-box;
}
#f3:hover {
  box-shadow: 0 0 11px rgba(33, 33, 33, 0.514); 
}
.booktitle{
  position: absolute;
  writing-mode: vertical-lr;
  font-size: 50px;
  left:360px;
  top:150px;
  color: #ebf2ff;
  text-shadow: shadow1, shadow2, shadow3;
  text-shadow: 4px 3px 0px rgba(71, 71, 71, 0.637), 9px 8px 0px rgba(0,0,0,0.15);
}
.prompt{
  position: absolute;
  writing-mode: vertical-lr;
  font-size: 25px;
  left:585px;
  top:950px;
  color: rgb(75, 75, 75);
  animation:neon-shine 2s linear infinite; 
}
.acontainer{
  position: absolute;
  width: 573px !important;
  left: 799px;
  top: 300px;
}
.ifm{
  position: relative;
  width: 566px;
  height: 219px;
  left: 0px;
  top: 0px;
  background-position: center;
  background-size: cover;
  background-image: url('../assets/pics/i.png');
}
.t1{
  font-family: Roboto;
  font-size: 25px;
  font-style: normal;
  font-weight: 400;
  line-height: 29px;
  letter-spacing: 0.28em;
  text-align: left;
  margin-top:10px;
}
.t2{
  font-family: Roboto;
  font-size: 15px;
  font-style: normal;
  font-weight: 400;
  line-height: 18px;
  letter-spacing: 0.28em;
  text-align: left;
  margin-top: 10px;
  margin-left: 10px;
}
.m1{
  margin-right: 10px;
  width: 208px;
  height: 133px;
  background: linear-gradient(0deg, rgba(255, 255, 255, 0.37), rgba(255, 255, 255, 0.37)), url('../assets/pics/3.png');

  background-position: center;
  background-size: cover;
  display: inline-block;
}
.intro{
  position: absolute;
  width: 214px;
  height: 50px;
  left: 0px;
  top: 500px;

  font-family: Roboto;
  font-size: 36px;
  line-height: 50px;
  letter-spacing: 0.28em;
  color: #606060;
}
.line{
  position: absolute;
  width: 1370px;
  height: 4px;
  left: 0px;
  top: 550px;
  background: #8a8a8a;
}
.vid{
  position: absolute;
  top:590px;
  left:700px;
  border:4px solid #bdbdbd
}
.hl{
  position: absolute;
  width: 500px;
  height: 300px;
  top:1200px;
}
.image-container {
  border-radius: 3px;
  overflow: hidden;
  position: relative;
  width: 100%;
  padding-top:75%;
}
.image-container:hover{
  box-shadow: 0 0 11px rgba(33, 33, 33, 0.514); 
}
img {
  object-fit: cover;
  width:180.33px;
  height: 135.24px;
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
}
@keyframes neon-shine{
  0%{opacity:1;}
  50%{opacity:0;}
  100%{
  color:#ffffff;}
}  
</style>