<template>
<div>
<button type="button" @click="add">Addition</button>
<button type="button" @click="subtract">Subtract</button>
<button type="button" @click="multiply">Multiply</button>
<button type="button" @click="divide">Divide </button>
</div>
</template>
<script>
export default {
props:["firstnumber","secondnumber"],
data(){
    return{
        result:0,
    }
},
methods:{
add:function(){
   this.$emit('result',parseInt(this.firstnumber) + parseInt(this.secondnumber))
},
subtract:function(){
   this.$emit('result',parseInt(this.firstnumber) - parseInt(this.secondnumber))
},
multiply:function(){
   this.$emit('result',parseInt(this.firstnumber) * parseInt(this.secondnumber))
},
divide:function(){
   this.$emit('result',parseInt(this.firstnumber) / parseInt(this.secondnumber))
}
}
}
</script>