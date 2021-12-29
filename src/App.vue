<template>
  <!-- img alt="Vue logo" src="./assets/logo.png" / -->

  <div style="display:flex;">
    <div @click="setView(0)">Plus  </div>
    <div @click="setView(1)"> | Minus</div>
    <div @click="setView(2)"> | Alpha</div>
  </div>
  <Plus v-show="isViewPlus" />
  <Minus v-show="isViewMinus" />
  <Alpha v-show="isViewAlpha" />
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Plus from './components/Plus.vue'
import Minus from './components/Minus.vue'
import Alpha from './components/Alpha.vue'
  
export default {
  components: {
    HelloWorld, Plus, Minus, Alpha
  },
  data() {
    return {
      isView : true,
      isViewPlus : true,
      isViewMinus : false,
      isViewAlpha: false,
    }
  },
  methods: {
    setView(id) {
      this.isViewPlus = false;
      this.isViewMinus = false;
      this.isViewAlpha = false;
      
      if(id == 0) 
        this.isViewPlus = true;
      else if(id == 1)
        this.isViewMinus = true;
      else if(id == 2)
        this.isViewAlpha = true;
    }
  }
}  
  
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 10px;
}
</style>