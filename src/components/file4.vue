<template>
    <h1> It is Class IV </h1>
    <div>{{this.mH1}} </div>
    <div v-html="mH1" > </div>
    <button v-on:click="myFun1">Click Me</button>
    <div v-html="mH2" > </div>
    <h3 class="c1"> Hello Change... </h3>
    <input v-on:keyup="myTable" v-model="fName" placeholder="Enter First Name" />
    <input v-model="lName" placeholder="Enter Last Name" />
    <h1> {{this.fName}} </h1>
    <button v-on:click="myFun2">Click Me</button>   
    <button v-on:click="myTable">Generate Table</button>   

    <div v-html="mTable">
    
    </div>
    <MyFile1></MyFile1>
</template>


<script>

import MyFile1 from './file1.vue'

export default {
    name : 'MyFile4',
    components:
    {
        MyFile1
    },
    data(){
        return{
            mH1 : "<h1> Hello it is HTML TAg </h1>",
            mH2 :'',
            fName:'',
            lName:'',
            mTable : ''
        }
    },
    methods:
    {
        myFun1()
        {
            // this.mH1 = "<h1> Hello Change </h1>"
            // this.mH1 += "<h2 style='color:red'> Hello Change </h2>"
            this.mH2 += "<h3 class='c1'> Hello Change </h3>"
        },

        myFun2()
        {
            alert (this.fName + ' ' + this.lName)
        },

        myTable()
        {
            let str = ''
            for (let i = 1 ; i <= 10 ; i++)
            {
                str += '<h1> ' + this.fName + ' X ' + i + ' = ' + ( this.fName * i) + ' </h1>'
            }
            this.mTable = str

        }
    }
}
</script>

<style>
.c1{
    width :400px;
    height :100px;
    border: 1px solid red;
}
</style>