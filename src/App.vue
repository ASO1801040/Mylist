<template>
  <div id="app">
    
    <MyList v-bind:title="title"
             v-on:item-event="appAction" />
    <hr>
    <div><table v-html="list" align="center"></table></div>
  </div>
</template>

<script>
import MyList from './components/Mylist.vue'

export default {
  name: 'App',
  components: {
    MyList
  },
  data: function() {
      return {
        title: 'メモを入力してください',
        result:[],
      }
  },
  computed:{
    list:function(){
      var table = '<tr><th> my list2 </th></tr>';
      for(var i in this.result){
        table += '<tr><td>'+ this.result[i] + '</td></tr>';
      }
      return table;
    }
  },
  methods:{
    appAction: function(item){
      this.result.unshift([item]);
      if(this.result.length>5){
        this.result.pop();
      }
    }
  }
  
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
table{
  border:1px solid gray;
}
tr th{
  background-color:black;
  color:white;
}
</style>
