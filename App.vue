<template>
 <div class="layui-form">
     <div>
            <label>姓名:</label>
            <input type="text"  v-model="person1.name">
     </div>
     <div>
            <label>学号:</label>
            <input type="text"  v-model="person1.num">
     </div>
     <div>
            <label>成绩:</label>
            <input type="text"  v-model="person1.score">
     </div>
            <button class="layui-btn layui-btn-normal" v-on:click="addPerson()">添加</button>
        <table class="layui-table">
            <thead >
                <tr>
                    <th style="text-align: center;">姓名</th>
                    <th style="text-align: center;">学号</th>
                    <th style="text-align: center;">成绩</th>
                    <th style="text-align: center;">删除</th>
                </tr>
            </thead>
            <tbody>
                <tr  v-for="person in people">
                    <td>{{person.name}}</td>
                    <td>{{person.num}}</td>
                    <td>{{person.score}}</td>
                    <td><button class="layui-btn layui-btn-normal" @click="delPerson(person)">删除</button></td>
                </tr>
            </tbody>
        </table>
    </div>
    
</template>

<script>
export default {
	 data(){
     return({
        person1:{
                        name:'',
                        num: '',
                        score: ''
                },
                people:[{
                    name: '王',
                    num: '666',
                    score: '1'
                },
                {
                    name: '帅',
                    num: '666',
                    score: '2'
                },
                {
                    name: '康',
                    num: '666',
                    score: '3'
                },
                ]
     })
   },

   methods:{
     addPerson(){
         this.person1.id=this.people.length+1;
          this.people.push(this.person1);
          this.person1={};
     },
     delPerson(person){
          this.people.splice(this.people.indexOf(person),1);
     }
   }
}
</script>

<style>
table{
  border: 1px solid red;
  text-align: center;
}
div{
    margin-bottom: 10px;
}
</style>
