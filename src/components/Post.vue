<template lang='pug'>
  #Post
    v-card.mx-auto(width='400' height='350')
      v-img(v-bind:src='imgurl' height='200px')
      v-card-title {{title}}
      v-card-subtitle {{subtitle}}
      v-card-actions
        v-btn(color='orange lighten-2' text='') Explore
        v-spacer
        v-btn(icon='' @click='show = !show')
          v-icon {{ show ? 'mdi-chevron-up' : 'mdi-chevron-down' }}
      v-expand-transition
        div(v-show='show')
          v-card.mx-auto.s(width='400')
            v-card-text {{message}}

</template>

<script>
  export default {
    name: 'Post',
    props:{
      title: String,
      subtitle: String,
      message: String,
      imgurl: String,
    },
    data: () => ({
      show: false,
    }),
  }
</script>

<style lang="scss" scoped>
.s{
  z-index: 100;
}
</style>
