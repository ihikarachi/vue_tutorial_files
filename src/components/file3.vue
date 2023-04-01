<template>
    <h1> My File 3 : {{msg}}</h1>
    <h1 v-if="var1 >= 3"> HEllo Test IF </h1>
    <h1 v-else-if="var1 < 3"> HEllo Test IF22123213 </h1>
    <h1 v-else > it is else </h1>
    <button v-on:click = "myFun(msg)"> Click Me </button>
    <ol>
        <li v-for="item in var2" :key="item">{{ item }}</li>
    </ol>

    <table border="1">
        <tr> 
            <td> ID </td>
            <td> Emp Name  </td>
            <td> Salary </td>
            <td> Depart </td>
        </tr>

         <tr v-for="emp in var3" :key="emp.id"> 
            <td> {{emp.ID}} </td>
            <td> {{emp.eName}} </td>
            <td> {{emp.Salary}} </td>
            <td> {{emp.DPT}} </td>
        </tr>
    </table>

</template>

<script>
export default {
    name : 'MyFile3',
    props:
    {
        msg:String
    },
    methods:
    {
        myFun(a)
        {
            alert(a)
            this.var1++;

            this.var2.map ((i) => 
            {
                alert(i);
            })
            // if (a == 'Hello it is propssadas dsa')
            // {
            //     alert('A')
            // }
            // else
            // {
            //     alert('B')
            // }

            // for (let i = 1 ; i<=5;i++)
            //     alert(i)
            // let i = 1
            // while(i<=6)
            // {
            //     alert(i);
            //     i++;
            //     if (i==2)
            //     break;
            // }
            // let i = 1
            // do{
            //     alert(i);
            //     i++;
            //     if (i==3)
            //     break;
            // }while(i<=5);

        },
        
    },
    data(){
        return{
            var1 : 1,
            var2 : ['ABCD','XYZ','Hello iHi','Test'],
            var3 : [
                {ID:1, eName: 'Saleem', DPT: 'IT' , Salary: 50000},
                {ID:2, eName: 'Kareem', DPT: 'Accounts' , Salary: 60000},
                {ID:3, eName: 'Raheem', DPT: 'IT' , Salary: 80000},
                {ID:4, eName: 'Arif', DPT: 'IT' , Salary: 90000},
                

            ]
        }
    }
}
</script>