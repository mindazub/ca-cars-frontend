<template>
  <div id="app">
    
    <navigation></navigation>
    
    <main>
    <router-view/>
    </main>

  </div>
</template>

<style lang="scss">
  
</style>

<script>
// @ is an alias to /src

import navigation from '@/components/masterpage/navigation.vue'

export default {
  components: {
        navigation
  },
  data(){
    return {

    }
  },
  created(){
    
  },
  methods:{
    
  }
}
</script>

