<template>
  <ul>
    <li v-for="(item,key) in data">{{item}}</li>
  </ul>
</template>

<script>
export default {
  name: 'App',
  data(){
    return{
      data:[]
    }
  },
  mounted:function(){
    this.$http.get('/api/data').then(res=>{
      this.data=res.data;
      console.log(res)
    })
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
