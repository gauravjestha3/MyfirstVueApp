<template>
  <div id="app">
    <label>Enter first Number</label>
    <input type="text"  @keyup="checking()" v-model="firstnumber"  required/>
    <label>Enter second number</label>
    <input type="text" @keyup="checkingsecondnumber()"v-model="secondnumber" required/>
   <div class="calculator-result" >Result:{{this.result }}</div>
   <app-child v-bind:firstnumber="firstnumber" v-bind:secondnumber="secondnumber" 
   v-on:result="showresult($event)"></app-child>
  </div>
</template>

<script>
import Child from './components/Child.vue'
export default {
  name: 'App',
components:{
'app-child':Child
},
data(){
  return{
    firstnumber:"",
    secondnumber:"",
    result:0
}},
methods:{
showresult:function(show){
  this.result=show
},
checking:function() {
  var regexNumbers = /[^0-9-]*/g;                       
  this.firstnumber=this.firstnumber.replace(regexNumbers,'');
},
checkingsecondnumber:function() {
  var regexNumbers = /[^0-9-]*/g;                       
  this.secondnumber=this.secondnumber.replace(regexNumbers,'');
},
}
}
</script>

<style>

</style>
