<template lang='pug'>
#About
  .v-container.d-flex.align-center.fbox
    v-img(v-bind:src='big' height='500px' width='700px')
    v-card.d-flex.align-center.justify-center.fcard(width='700px' height='400px')
      .v-container
        .row.d-flex.align-center.justify-center
          v-card-title.text-h3 公共冰箱清理
        .row
          .content
            p.text-center.text-h5 就是今天!
            p.text-center 本周日(12/20)晚上十點，齋團隊會清理公共冰箱，
            p.text-center 所有不在表單上、影響冰箱整潔的物品，將會被清出。
            p.text-center 請有在使用冰箱的齋民注意一下自己是否有拍照登記。
            p.text-center 📷📷📷📷📷📷
  .newsbox
    .rowbox.d-flex.justify-space-between
      Post(v-bind:title='title', v-bind:subtitle='subtitle',  v-bind:imgurl='imgurl', v-bind:message='message')
      Post(v-bind:title='title', v-bind:subtitle='subtitle',  v-bind:imgurl='imgurl', v-bind:message='message')
      Post(v-bind:title='title', v-bind:subtitle='subtitle',  v-bind:imgurl='imgurl', v-bind:message='message')
    .rowbox.d-flex.justify-space-between
      Post(v-bind:title='title', v-bind:subtitle='subtitle',  v-bind:imgurl='imgurl', v-bind:message='message')
      Post(v-bind:title='title', v-bind:subtitle='subtitle',  v-bind:imgurl='imgurl', v-bind:message='message')
      Post(v-bind:title='title', v-bind:subtitle='subtitle',  v-bind:imgurl='imgurl', v-bind:message='message')
      
</template>
<script>
  import Flipbook from 'flipbook-vue';
  import Post from '@/components/Post.vue'
  export default {
      name: 'About',
      data() {
        return {
          pages: [null,require("../assets/pics/ppt/1.png"),
                require("../assets/pics/ppt/2.png"),
                require("../assets/pics/ppt/3.png"),
                require("../assets/pics/ppt/4.png"),
                require("../assets/pics/ppt/5.png"),
                require("../assets/pics/ppt/6.png")],
          big:require('@/assets/pics/news/p1.png'),
          title:'【歡迎報名】影像工作坊 11/29(日)',
          subtitle:'講者：潘信安（熱青年）時間 : 2020/11/29(日) 9:00-17:00',
          imgurl:require('@/assets/pics/news/p3.jpg'),
          message:'誰都可以拿起手機開始自稱我在拍片，但一切最挑戰的是如何構思好敘事方式，並用影像說故事。看到這別抱太大期望，一天的課本來就沒辦法教會你成為名導演，但絕對可以讓你帶走基本敘事能力，實作拍攝後，接下來創作的路就是你的了！'

        }
      },
      components: { Flipbook, Post}
  }
</script>
<style lang="scss" scoped>
.flipbook {
  z-index: 1;
}
.fbox{
  position: absolute;
  left: 5vw;
  top:2vh;
}
.a{
  position: absolute;
  top:500px;
}

.fcard{
  background-color: rgba(226, 244, 245, 0.774);
}
.newsbox{
  position: absolute;
  top:80vh;
  left:5vw;
  width:90vw;
}
.rowbox{
  margin-bottom: 50px;
}
</style>
