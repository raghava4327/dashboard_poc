<template>
  <div class="app">
  <NavBar />
  <TopBoard />
  <BottomBoard />
  </div>
</template> 
<script>
import NavBar from './components/Navbar.vue'
import TopBoard from './components/TopBoard.vue'
import BottomBoard from './components/BottomBoard.vue'
export default {
  name: 'App',
  components: {
    NavBar,
    TopBoard,
    BottomBoard
  }
} 
</script>

<style>

</style>
