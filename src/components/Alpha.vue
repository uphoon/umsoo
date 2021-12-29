<template>

<div class="outer" @click="getMakeNum()">
<div class="inner mdc-typography--headline1">


<div class="flex-end">
{{qNum.Q01}}
</div>
  
<div class="flex-between">
</div>
  
<div class="flex-end">
<div v-show="isRsltShow">{{qNum.SUM}}</div>
</div>

  
</div>
</div>

</template>

<script>

import {CountUp} from "countup.js"

  
export default {
  data(){
    return {
      qNum : {
        Q01: 0,
        Q02: 0,
        SUM:0
      },
      isRsltShow : true,
      qList : [
        "A", "B", "C", "D", "E",
        "F", "G", "H", "I", "J",
        "K", "L", "M", "N", "O",
        "P", "Q", "R", "S", "T",
        "U", "V", "W", "X", "Y",
        "Z"
      ]
    }
  },
  created : function(){
    this.getMakeNum();
  },
  methods: {
    getMakeNum () {
      
      this.isRsltShow = !this.isRsltShow;

      if(this.isRsltShow) return ;

      var qn1 = 0;
      var qn2 = 0;
      
      qn1 = Math.floor(Math.random() * 26);
      
      this.qNum.Q01 = this.qList[qn1];
      
      this.qNum.SUM = this.qList[qn1].toLowerCase();

    }
  }
}
  
</script>


<style scoped>

html, body {
  height: 90%;
  font-family: serif;
}

div {
  border: 0 red solid;
  margin: 0;
  padding: 3px;
  font-family: serif;
}

hr {
  border: 1px #cccccc solid;
  color : #cccccc;
  text-align: center;
  margin: 5px 0 5px 0;
}
      
.center {
  display: flex;
  justify-content: center;
  align-items: center;
}

.outer {
  display: flex;
  margin-top : 50px;
}

.inner {
  width:50%;
  margin: auto;
}

#eq2 {
  display: none;
}

.flex-end {
  text-align: center;
  justify-content:flex-end;
}

.flex-between {
  display: flex;
  justify-content:space-between;
  height : 50px;
}

.plusMark {
  align-self:flex-end;
}
@media screen and (orientation: landscape) {
  .outer {
    display: flex;
    margin-top : 10px;
  }
  .inner {
    display: flex;
    margin: auto;
  }
  #eq1 {display: none;}
  #eq2 {
    display: block;
    padding: 0 25px 0 25px;
  }
  .flex-between {
    display: flex;
    justify-content:space-between;
    width : 50px;
  }
  .plusMark {
    align-self:center;
    padding: 0 25px 0 25px;
  }
}
  
</style>