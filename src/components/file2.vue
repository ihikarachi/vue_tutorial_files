<template>
<center>
    <div style="background:pink;margin:6px">
        
    <h1> Hello iHi {{ this.var1 }}</h1>
    <h2> {{msg}} </h2>
    <h3> {{Number(n1)   + Number(n2)}} </h3>
    <div class="MyDiv1"> </div>
    <div v-on:mouseover="myFun1" class="MyDiv1"> </div>
    <button v-on:click="myFun1"> Click Me </button>
    <button v-on:click="myFun2(2,3)"> Click Me </button>
    
    </div>
    </center>
</template>

<script>
export default {
    name: 'MyFile2',
    props: 
    {
        msg:String,
        n1:String,
        n2:String
    },
    methods:
    {
        myFun1()
        {
            // alert('HEllo i am alert')
            this.var1++
        },
        myFun2(a,b)
        {
            
            alert(a+b)
            // alert(this.props.msg)
        },
        
        },
        data(){
            return{
                var1 : 1
            }
    }
}
</script>

<style>
.MyDiv1{
    background: yellow;
    border: 2px solid black;
    width: 200px;
    height: 300px;
    border-radius: 20px;
    box-shadow: 2px 5px 7px yellow;
    margin: 5px;
    padding: 5px;
}
</style>