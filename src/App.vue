<template>
  <div id="app">
    <router-view/>
    <FooterGuide v-show="$route.meta.showFooter"/>
  </div>
</template>

<script>
  import FooterGuide from './components/FooterGuide/FooterGuide.vue'
  import {mapActions} from 'vuex'

  export default {

    mounted(){
      // this.$store.dispatch('getAddress')
      this.getAddress()
    },

    methods:{
      ...mapActions(['getAddress'])
    },

    components:{
      FooterGuide
    }
  }
</script>

<style lang="stylus" ref="stylesheet/stylus">
  .app
    width 100%
    height 100%
    background #f5f5f5
</style>
