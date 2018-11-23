<template>
  <section class="users">
    <User
      v-for="user in users"
      :key="user.id"
      thumbnail="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcS_RcvQwMUcUUmXkMQpOnNSqqv7cPiBlH5uCIQXqgvqfUOmcV9x"
      :name="user.name"
      :email="user.email"
      :id="user.id"/>
  </section>
</template>

<script>
import User from '@/components/User'
import axios from 'axios'
export default {
  components: {
    User
  },
  title: '',
  async asyncData () {
    const {data} = await axios.get('https://jsonplaceholder.typicode.com/users')
    return {users:data}
  }
};
</script>

<style scoped>
.users {
  display: flex;
  flex-flow: row wrap;
  justify-content: center;
  align-items: center;
  margin: 10px;
}
</style>
