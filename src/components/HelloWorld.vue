<template>
 <h1 v-bind:style="{color:'red'}">Test</h1>
 <h1 v-bind:class="{MyDiv:true}">Test</h1>
 <h1 class="MyDiv">Test</h1>
 <h1 v-bind:class="{MyDiv2:false,MyDiv:true}">Test</h1>
 <h1 v-bind:class="[sh?'MyDiv':'MyDiv2']">Tssssest</h1>
 
</template>

<script>


export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data(){
    return{
      sh:false
    }
  }
}
</script>

<style >
.MyDiv{
  color: pink;
}

.MyDiv2{
  color: blueviolet;
}
</style>
