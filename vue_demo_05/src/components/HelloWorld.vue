<template>
  <div>
    <input type="button" value="发送请求" @click="handleSend"/>
  </div>
</template>

<script>
import axios from "axios"

export default {

  methods: {
    handleSend() {
      //通过axios发送http请求
      axios.post('/api/admin/employee/login', {
        username: 'admin',
        password: '123456'
      }).then(res => {
        console.log(res.data)
      }).catch(error => {
        console.log(error.response)
      })
    }
  }


}
</script>

<style>
</style>
