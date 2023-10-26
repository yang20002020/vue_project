<template>
  <div>
    <input type="button" value="发送POST请求" @click="handleSendPost"/>
    <input type="button" value="发送GET请求" @click="handleSendGet"/>
    <input type="button" value="统一请求" @click="handleSend"/>
  </div>
</template>

<script>
import axios from "axios"

export default {

  methods: {
    handleSendPost() {
      //通过axios发送POST请求
      axios.post('/api/admin/employee/login', {
        username: 'admin',
        password: '123456'
      }).then(res => {
        console.log(res.data)
      }).catch(error => {
        console.log(error.response)
      })
    },

    handleSendGet(){
     //通过axios发送get方式请求
      axios.get('/api/admin/shop/status', {
        headers:{
          token:'eyJhbGciOiJIUzI1NiJ9.eyJlbXBJZCI6MSwiZXhwIjoxNjk4MzI3NjMyfQ.9ffAOMRoOwWvJDje22ldvSrPTuvYWdKv2Zv6jqDRBuI'
        }
      }).then(res => {
        console.log(res.data)
      }).catch(error => {
        console.log(error.response)
      })
    },
    handleSend(){
      //使用axios提供的统一调用方式发送请求
      axios({
             url: '/api/admin/employee/login',
             method: 'post',
              data:{
               //data表示通过请求体传参
                username: 'admin',
                password: '123456'
              }
          }).then(res=>{
          console.log(res.data.data.token)
          axios({
            url:'/api/admin/shop/status',
            method: 'get',
            headers: {
              token: res.data.data.token
            }
          })
      })
    }

  }


}
</script>

<style>
</style>
