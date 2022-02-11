<template>

<div class="outer" @click="getMakeNum()">
<div class="inner mdc-typography--headline1">


<div class="flex-end">
<div id="q01">{{qNum.Q01}}</div>
</div>
<div class="flex-between">
<div class="mdc-typography--headline3 plusMark">+</div>
<div id="q02">{{qNum.Q02}}</div>
</div>

  <div>
    <div id="eq1"><hr/></div>
    <div id="eq2">=</div>
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
      isRsltShow : true
    }
  },
  created : function(){
    this.getMakeNum();
  },
  methods: {
    getMakeNum () {
      
      this.isRsltShow = !this.isRsltShow;

      if(this.isRsltShow) return ;

      var sum = 0;
      var qn1 = 0;
      var qn2 = 0;

      do{
        qn1 = Math.floor(Math.random() * 10);
        qn2 = Math.floor(Math.random() * 10);
        sum = qn1 + qn2;
      }while((sum > 10) ||
            (qn1 == 0 || qn2 == 0 ));

      this.qNum.Q01 = qn1;
      this.qNum.Q02 = qn2;
      this.qNum.SUM = qn1 + qn2;
/*
      var countUp01 = new CountUp("q01", qn1);
      var countUp02 = new CountUp("q02", qn2);
      
      countUp01.start();
      countUp02.start();
*/
    }
  }
}
  
</script>


<style scoped>

html, body {
  height: 90%;
}

div {
  border: 0 red solid;
  margin: 0;
  padding: 3px;
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
  justify-content: center;
  align-items: center;
  min-height: 100vh;
}

.inner {
  width:50%;
  margin: auto;
}

#eq2 {
  display: none;
}

.flex-end {
  display: flex;
  justify-content:flex-end;
}

.flex-between {
  display: flex;
  justify-content:space-between;
}

.plusMark {
  align-self:flex-end;
}
@media screen and (orientation: landscape) {
  .inner {
    display: flex;
    margin: auto;
  }
  #eq1 {display: none;}
  #eq2 {
    display: block;
    padding: 0 25px 0 25px;
  }
  .plusMark {
    align-self:center;
    padding: 0 25px 0 25px;
  }
}
  
</style>