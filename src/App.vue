<template>
  <div id="app">
    <ul>
      <li v-for="item in user" :key="item.id">{{ item.name }}</li>
    </ul>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'App',
  data() {
    return {
      user: []
    }
  },
  mounted() {
    axios.get('http://localhost:3000/api/user').then(res => {
      this.user = res.data
    })
  }
}
</script>

<style>
</style>
