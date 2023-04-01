<template>
<div style="width:100%; background:yellow">
    <center>
        <h1> {{gdr}} </h1>
    <h1 v-if="var1=='iHi'" class="MyDiv1"> Hello It is Vue1: </h1>
     <h1 v-else class="MyDiv1"> Hello It is Vue2 </h1>
     <h1> {{sub}} </h1>
     <div v-html="mHTML"> </div>
     <input v-model="emp.fName" placeholder="Enter First Name" />
     <input v-model="emp.lName" placeholder="Enter Last Name" />
     <input v-model="var1" placeholder="Enter Last Name" />
     <br/>
     <div>
     Male: <input v-model="gdr" type="radio" value="Male" id="M1"/> 
      Female: <input v-model="gdr"  type="radio" value="FMale" id="M2"/> 
     </div>

     <div>
        <input v-model="sub" type="checkbox" value="eng" />
        <input v-model="sub" type="checkbox" value="math" />
        <input v-model="sub" type="checkbox" value="urdu" />

     </div>
    <h2> {{msg}} </h2>

   

    <h2> {{ Number(n1)  + Number(n2)}} </h2>
    <h3> {{var1}} </h3>
    
    <h1 v-for="item in users" :key="item.id"> {{item.id}} {{item.name}}{{item.salary}}</h1>
    
    <button v-on:click="myFun1()"> Click me </button>
    <button v-on:click="myFun2()"> Click me </button>

    
    </center>
    </div>
</template>

<script>
export default {
    name: 'MyFile1',
    props: {
        msg:String,
        n1:String,
        n2:String
    },
    methods:
    {
        myFun2()
        {

        },
        myFun1()
        {
            // alert('Test')
            let str1 = ''
            this.var1 = 'iHi'
            alert(this.emp.fName + ' ' + this.emp.lName);
            this.users.map (
                (va)=>
                {
                    // alert(va.name)
                    str1 += va.name  + ','
                }
            )
            this.mHTML = "<h1>" + str1 + "</h1>"

        }
    },  
    data() {
        return{
                var1:'Hello',
                mHTML:'<b> xvxHello </b>',
                users: [
                    {id:1,name:'Shakeel 1',salary:60000},
                    {id:2,name:'Shakeel 2',salary:70000},
                    {id:3,name:'Shakeel 3',salary:80000},
                    {id:4,name:'Shakeel 4',salary:90000},
                ],
                emp:{fName:'',lName:''},
                sub:[],
                gdr:''
                
        }
    }
    
}
</script>

<style>
.MyDiv1 {
    width: 100px;
    height: 100px;
    background: rebeccapurple;
    color: aliceblue;
    font-size: large;
}
</style>