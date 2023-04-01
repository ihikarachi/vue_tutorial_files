<template>
    <h1 class="MyDiv1"> My File 5 </h1>
    <div v-html="myHTML">  </div>
    <input v-if="Sub1" v-on:keyup= "myResult" v-model="var1" placeholder="Enter Math Marks" />
    <input v-if="Sub2" v-on:keyup= "myResult" v-model="var2" placeholder="Enter English Marks" />
    <input v-if="Sub3" v-on:keyup= "myResult" v-model="var3" placeholder="Enter Urdu Marks" />
    <button v-on:click= "myResult" >Generate Result</button>
    <br />
    Male: <input v-model="Gender" type="radio" value="Male">
    Female: <input v-model="Gender" type="radio" value="FMale"> 
    <br />
    Math: <input type="checkbox" v-model="Sub1" value="Math">
    Urdu: <input type="checkbox" v-model="Sub2" value="Urdu">
    English: <input type="checkbox" v-model="Sub3" value="English">


    <h3> {{Total}}</h3>
    <h3> {{Per}}</h3>
    <h1 v-bind:class="[Grade == 'Fail' ? 'failClass' : 'passClass']"> {{Grade}}</h1>
    <h4  > {{Gender}} </h4>
    <h1> {{Subject}} </h1>

    <h3 >{{Sub1}} </h3>

    <MyFile3 v-for="item in varX" :key="item" :msg='item'></MyFile3>
    

</template>



<script>

import MyFile3 from './file3.vue'


export default {
    name: 'MyFile5',
    components:
    {
        MyFile3
    },
    data(){
        return{
        myHTML : '<h2> Hello iHi </div>',
        var1:'',
        var2:'',
        var3:'',
        Total:'',
        Per:'',
        Gender:'',
        Subject : [],
        Sub1:true,
        Sub2:true,
        Sub3:true,
        varX:['C++','React','Python','Vue JS'],
        Grade:'None'
        }
    },
    methods:
    {
        myResult()
        {
            let sum = Number(this.var1) +  Number(this.var2) +  Number(this.var3)
            this.Total = sum

            if (this.Sub1 && this.Sub2 && this.Sub3)
                 this.Per = sum * 100 / 300
            else if (this.Sub1 && this.Sub2 )
                 this.Per = sum * 100 / 200
            else if (this.Sub1 && this.Sub3 )
                 this.Per = sum * 100 / 200
            else if (this.Sub2 && this.Sub3 )
                 this.Per = sum * 100 / 200

            else 
                 this.Per = sum * 100 / 100
             
                 
            if  (this.Per > 90)
                this.Grade = 'A+'
            else if (this.Per >= 80 && this.Per <= 90)
                this.Grade = 'A'
            else if (this.Per >= 70 && this.Per <= 80)
                this.Grade = 'B'
            else 
                this.Grade = 'Fail'
        }
    }
}
</script>

<style>
.MyDiv1{
    color: red;
}

.passClass
{
    color: blue;
}

.failClass
{
    color:red
}
</style>