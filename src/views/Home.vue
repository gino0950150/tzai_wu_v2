<template lang='pug'>
#Home
  .frame
  .f3
    .ifm
    .t1 【移工人生體驗桌遊，最後一場！】
    .t2  我們想要別人怎麼對待台灣人 要先從友善的對待移工開始。
    .container 
      .m1
      .m1
      .m1
      .m1
      .m1
  .div.intro 書院介紹
  .div.line 
  flipbook.flipbook(v-bind:pages="pages", singlePage = true, canZoomIn = 0, canZoomOut = 0)
  .prompt ⇣翻頁
  iframe.vid(width='670' height='430' src='https://www.youtube.com/embed/7yS0Y-nI_L0' frameborder='0' allow='accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture' allowfullscreen='')
</template>
<script>
// @ is an alias to /src
import Flipbook from 'flipbook-vue';
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
        }
  },
  components: { Flipbook },
  beforeCreate(){
    console.log('files')
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
  animation: image 20s infinite alternate;
}
@keyframes image {
  0% {
    background-image: url('../assets/pics/2.png');
  }
  20% {
    background-image: url('../assets/pics/3.png');
  }
  40% {
    background-image: url('../assets/pics/3.png');
  }
  60% {
    background-image: url('../assets/pics/4.png');
  }
  80% {
    background-image: url('../assets/pics/7.jpg');
  }
  100% {
    background-image: url('../assets/pics/8.jpg');
  }
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
  left: 0px;
  top : 270px; 
}
.f3{
  position: absolute;
  width: 573px;
  height: 307px;
  left: 799px;
  background: #FFFFFF;
  border: 4px solid #E1E1E1;
  box-sizing: border-box;
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
  left:575px;
  top:950px;
  color: rgb(75, 75, 75);
  animation:neon-shine 2s linear infinite; 
}
.container{
  position: absolute;
  height: 133px;
  width: 573px;
  left: -4px;
  top: 320px;
  overflow-x: scroll;
  overflow-y: hidden;
  white-space: nowrap;
}
.container::-webkit-scrollbar {
  height: 8px;
}
.container::-webkit-scrollbar-track {
  background: #FFFFFF;
  border: 1px solid #D8D8D8;
}
.container::-webkit-scrollbar-thumb {
  background: #d3d3d3;
}
.container::-webkit-scrollbar-thumb:hover {
  background: rgb(207, 207, 207);
}
.container::-webkit-scrollbar-thumb:active {
  background: rgb(201, 201, 201);
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
@keyframes neon-shine{
  0%{opacity:1;}
  50%{opacity:0;}
  100%{
  color:#ffffff;}
}  
</style>