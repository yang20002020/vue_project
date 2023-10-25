<template>
  <div>
    <h1>{{name}}</h1>
    <h1>{{ age >60?'老年':'青年'}}</h1>

    <div><input type="text" v-bind:value="name"></div>
    <div><input type="text" :value="age"></div>
    <div><img :src="src"/></div>


    <div>
      <input type="button" value="保存" v-on:click="handleSave"/>
      <input type="button" value="保存" @click="handleSave"/><br>
    </div>
  </div>
</template>

<script>
export default{
   data(){
     return {
       name:'张三',
       age:30,
       src:'https://tlisa-web.oss-cn-beijing.aliyuncs.com/7a7b56e5-444d-4ed2-9850-f4f5bb2fb174.png'
     };
   },

   methods:{
     handleSave(){
        alert(this.name)
     }
   }
}
</script>

<style >
</style>
