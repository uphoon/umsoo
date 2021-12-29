<template>

<div class="outer" @click="getMakeNum()">
<div class="inner mdc-typography--headline1">

  <div id="wrp_work" style="display: flex;">
    <div style="width:45%">
      <div>&nbsp;</div>
      <div style="text-align: left; padding-top:2rem" class=" mdc-typography--headline3">+</div>
    </div>
    <div style="width:fill">
      <div id="q01">{{qNum.Q01}}</div>
      <div id="q02">{{qNum.Q02}}</div>
    </div>
  </div>

  <div id="wrp_line" class="center">
    <hr />
  </div>

  <div id="wrp_answ" style="display: flex;">
    <div  style="width:45%">
      &nbsp;
    </div>
    <div style="width: fill;">
      <div v-show="isRsltShow">{{qNum.SUM}}</div>
    </div>
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
  width: 80%;
  margin: 5px 0 5px 0;
}
      
.center {
  display: flex;
  justify-content: center;
  align-items: center;
}

.outer {
  display: flex;
  height: 100%;
}

.inner {
  width:50%;
  margin: auto;
}
  
</style>