<template>
  <div>
    <h1>{{name}}</h1>
    <h1>{{ age >60?'老年':'青年'}}</h1>
  </div>
</template>

<script>
export default{
   data(){
     return {name:'张三',age:30};
   }
}
</script>

<style >
</style>
