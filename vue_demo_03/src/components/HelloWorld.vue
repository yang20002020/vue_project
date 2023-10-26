<template>
  <div>
    双向绑定: {{name}}
    <input type="text" v-model="name">
    <input type="button" value="改变" @click="handleChange"/>
  </div>
</template>

<script>
 export default{
     data(){
       return {
         name:'张三'
       }
     },
     methods:{
       handleChange(){
         this.name='李四'
       }
     }
 }
</script>

<style >
</style>
