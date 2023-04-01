<template>
    <div class="MyDiv1"> Test v-bnd </div>
    <div class="MyDiv1" style="padding:10px"> Test v-bnd </div>
    <div v-on:click="myFun" v-bind:class="{MyDiv2:isStyle,MyDiv1:!isStyle}"> Test </div>
    <div v-bind:class="[i<0?'MyDiv2':'MyDiv1']" > : Test :  </div>
    <button v-on:click="myFun" > On / Off </button>
    <h1> {{i}} </h1>

</template>

<script>
export default {
    name: 'MyFile6',
    data(){
        return{
            isStyle:true,
            i : 20
        }
    },
    methods:
    {
        myFun(){
            // this.isStyle = ! this.isStyle
            this.i-=4
        }
    }
}
</script>

<style >
.MyDiv1
    {
        width: 100px;
        height: 100px;
        border: solid red 2px;
        border-radius: 5px;
        cursor: pointer;
    }
.MyDiv2
    {
        width: 100px;
        height: 100px;
        border: solid red 2px;
        border-radius: 105px;
        cursor: pointer;
    }
</style>