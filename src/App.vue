<template>
  <Navbar></Navbar>
  <div class="container">
    <router-view/>
  </div>
  
</template>

<script>
import Navbar from './components/Navbar.vue'
export default {
  name:'App',
  components:{
    Navbar,
  }

}
</script>

<style>
</style>
