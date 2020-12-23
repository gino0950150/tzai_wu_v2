<template lang='pug'>
#Home
  .camera
    .space
      .framebox
        .frame
      section.container
        #box.box.show-front
          figure.front
            .frontframe
              .subtitle 國立清華大學
              .subtitle 載物書院
          figure.back
            .frontframe
              .subtitle 自我探索
              .subtitle 產業創新
          figure.right
          figure.left
          figure.top
            .topframe
              .subtitle 服務學習
          figure.bottom
            .topframe
              .subtitle 自組小組
      .background
        flipbook.flipbook(v-bind:pages="pages", singlePage = false, canZoomIn = 0, canZoomOut = 0)
        .booktitle 書院介紹
        .prompt ⇣翻頁
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
  components: { Flipbook }
}
</script>
<style lang='scss'>
@import url(https://fonts.googleapis.com/css?family=Raleway);
@import'../assets/scss/main.scss';
//CONFIG
$box-width: 20vw;
$box-height: $box-width / 1.5;
$primary-color: $secondColor;
$secundary-color: #ebf2ff;;

* {
  box-sizing: border-box;
}
.container {
      width: $box-width;
      height: $box-height; 
      position: absolute;
      left: 69vw;
      top: 19vh;
      //border: 1px solid #CCC;
      perspective: 1200px;
    }

    .box {
      width: 100%;
      height: 100%;
      position: absolute;
      transform-style: preserve-3d;
      transition: transform 0.5s;
      figure {
          display: table;
          position: absolute;  
          text-align: center; 
          color:$mainColor;
      }
    }
    
    //Sizes
    .box .front,
    .box .back {
      width: $box-width;
      height: $box-height;
    } 
    .box .right,
    .box .left {
      width: $box-width / 3;
      height: $box-height;
    } 
    .box .top,
    .box .bottom {
      width: $box-width;
      height: $box-width / 3;
    }

    //Positions
    .box .right,
    .box .left {
      left: $box-width / 3;
    } 
    .box .top,
    .box .bottom {
      top: $box-height / 4;
    }

    //Colors
    .box .front,
    .box .back   { background: darken($secundary-color, 5%);}
    .box .right,
    .box .left,
    .box .top,
    .box .bottom { background: darken($secundary-color, 15%);}
    
    //Transforms
    .box .front  {
      transform: translateZ($box-height / 4);
    }
    .box .back   {
      transform: rotateX(-180deg) translateZ($box-height / 4);
    }
    .box .right  {
      transform: rotateY(90deg) translateZ($box-width / 2);
    }
    .box .left {
      transform: rotateY(-90deg) translateZ($box-width / 2);
    }
    .box .top {
      transform: rotateX(90deg) translateZ($box-height / 2);
    }
    .box .bottom {
      transform: rotateX(-90deg) translateZ($box-height / 2);
    }
    //Show Specific Face
    .box.show-front {
      transform: translateZ($box-height / -4);
    }
    .box.show-back {
      transform: translateZ($box-height / -4) rotateX(-180deg);
    }
    .box.show-right {
      transform: translateZ($box-width / -2) rotateY(-90deg);
    }
    .box.show-left {
      transform: translateZ($box-width / -2) rotateY(90deg);
    }
    .box.show-top {
      transform: translateZ($box-height / -2) rotateX(-90deg); 
    }
    .box.show-bottom {
      transform: translateZ($box-height / -2) rotateX(90deg);
    }
    
    //Rollover
    .box:hover {
      transform: rotateX(-180deg) translateZ($box-height / 4);
    }
    .frontframe{
      padding-top:3rem;
      font-size: 2.5rem !important;
    }
    .topframe{
      padding-top: 1.5rem;
      font-size: 2.5rem !important;
    }
@keyframes rotate {
  0% {
    transform: rotateX(0deg) rotateY(0deg);
  }
  20%{
    transform: rotateX(180deg) rotateY(0deg);
  }
  40%{
    transform: rotateX(90deg) rotateY(0deg);
  }
  80%{
    transform: rotateX(-90deg) rotateY(0deg);
  }
  100%{
    transform: rotateX(0deg) rotateY(0deg);
  }
}

.box {
  animation: rotate 30s infinite ease-in-out;
}
.frame {
  position: absolute;
  height: 64vh;
  width:55vw;
  left: 3vw;
  top: 2vh;
  background-color: #eee;
  background-position: center;
  background-size: cover;
  animation: image 20s infinite alternate;
  z-index: 2;
  -webkit-box-shadow: 9px 9px 28px -7px #000000; 
  box-shadow: 9px 9px 28px -7px #000000;
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
.camera{
    perspective-origin:center center;
    -moz-perspective-origin:center center;
    -webkit-perspective-origin:center center;
    perspective:500px;
    -moz-perspective:500px;
    -webkit-perspective:500px;
}
.space{
    width:100%;
    height:100%;
    transform-style:3d;
    -moz-transform-style:3d;
    -webkit-transform-style:3d;
    z-index: 2;
}
.framebox{
    z-index: 2;
}
.background{
  position: absolute;
  width: 94vw;
  top:70vh;
  left: 3vw;
  height: 500px;
  background-color: $mainColor;
  z-index: -1;
}
.flipbook {
  position: absolute;
  width: 1021px;
  height: 794px;
  z-index: 4;
  left: -870px;
  top : -300px; 
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
  right:422px;
  top:380px;
  color: #eee;
  animation:neon-shine 2s linear infinite; 
}
@keyframes neon-shine{
  0%{opacity:1;}
  50%{opacity:0;}
  100%{
  color:#ffffff;}
}  
</style>