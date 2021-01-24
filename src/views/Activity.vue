<template lang='pug'>
#Activity
  //- vue-horizontal-list.container(:items='items' :options='options')
  //-   template(v-slot:default='{ item }')
  //-     div
  //-       .image-container
  //-         img(:src='item.image')
</template>
<script>
  import VueHorizontalList from "vue-horizontal-list";
  export default {
    name: "image-three",
    components: {
      VueHorizontalList,
    },
    data() {
      return {
        items: [
          {
            image: require('@/assets/pics/news/p3.jpg'),
          },
          {
            image: "https://picsum.photos/id/1019/600/600",
          },
          {
            image: "https://picsum.photos/id/1039/600/600",
          },
          {
            image: "https://picsum.photos/id/1042/600/600",
          },
          {
            image: "https://picsum.photos/id/1044/600/600",
          },
          {
            image: "https://picsum.photos/id/1057/600/600",
          },
        ],
        options: {
          responsive: [
            { end: 576, size: 1 },
            { start: 576, end: 768, size: 2 },
            { size: 6 },
          ],
        },
      };
    },
  };
</script>
<style lang="scss" scoped>
.container{
  width: 300px;
}
.image-container {
  border-radius: 3px;
  overflow: hidden;
  position: relative;
  width: 100%;
  padding-top: 60%;
}
img {
  object-fit: cover;
  width: 208px;
  height: 200px;
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
}
#Activity{
  position: absolute;
  width: 1370px;
  height: 1021px;
  left: 68px;
  top: 91px;
}
</style>
