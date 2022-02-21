<template>
  <div id="app">
    <div class="counter">Counter: {{ samnumber }}</div>
        <div class="btn">

            <button v-on:click="add" class="btn1">追加</button>
            <button v-on:click="del(index)" class="btn1">リセット</button>
        </div>
       
        <table class="table">


            <tbody>
                <tr class="tbodyinfo" v-for="(user) in users" v-bind:key="user.id">
                    <td><input v-model="user.text"></td>
                    <td><input v-model="user.number" type="number"></td>
                </tr>
            </tbody>
        </table>
  </div>
</template>

<script>
export default {
  el:'#app',
  data () {
    return {
      msg: 'Hello World!',
      users: [{ text: '', number: '' }],
      samnumber: 0,
      i: 0,
      x: 0,

    }
  },
  methods:{
    add: function(){
      
      this.x = this.i
      this.users.push({ text: '', number: '' })
      if(this.users[this.x].number ==''){
        this.users[this.x].number = 0


      }
      
      this.samnumber = parseInt(this.samnumber) + parseInt(this.users[this.x].number)
      this.i = this.i + 1
      


    },
     del: function () {
        this.users = [{ text: '', number: '' }]
        this.samnumber = 0
        this.x = 0
        this.i = 0
      },
  

  },
    
    
}
</script>

<style>
.counter{
  text-align: center;

}
.btn{
  text-align: center;
}
.table{
  width: 100%;

}
.tbodyinfo td input{
   height: 50px;
   width: 100%;

}
.tbodyinfo td{
  height: 100%;
}
.btn1{
   min-width: 130px;
    height: 40px;
    color: black;
    padding: 5px 10px;
    font-weight: bold;
    cursor: pointer;
    transition: all 0.3s ease;
    position: relative;
    display: inline-block;
    outline: none;
    border-radius: 5px;
    border: none;
    background: #ced4da;
    box-shadow: 0 5px #adb5bd;

}
.btn1:hover{
  box-shadow: 0 3px #adb5bd;
  top: 1px;

}
.btn1:active{
  box-shadow: 0 0 #adb5bd;
  top: 5px;

}


</style>
