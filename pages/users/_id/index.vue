<template>
  <section class="single-user">
    <div>
      <h1>User Details</h1>
      <img class="img-container" src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcS_RcvQwMUcUUmXkMQpOnNSqqv7cPiBlH5uCIQXqgvqfUOmcV9x" alt="">
    </div>
    <h1>{{ $route.params.id }}</h1>
    <p>{{ name }}</p>
    <p>{{ username }}</p>
    <p>{{ email }}</p>
    <p>{{ address.street + ' ' + address.suite }}</p>
    <p>{{ phone }}</p>
    <p>{{ website }}</p>
    <p>{{ company.name}}</p>
    <p>{{ company.catchPhrase }}</p>
    <p>{{ company.bs }}</p>
  </section>
</template>

<script>
import axios from 'axios'

export default {
  validate ({ params }) {
    return !isNaN(+params.id)
  },
  async asyncData({params, error}){
    const {data} = await axios.get(`https://jsonplaceholder.typicode.com/users/${+params.id}`)
    return data
  }
}

</script>

<style scoped>
.single-user {
  display: grid;
  flex-flow: row;
  justify-content: center;
  align-items: center;
  text-align: center;
  padding: 10px;

  margin:10px 400px 10px 400px;
  
}
.img-container{    
    grid-column: 1;    
    text-align: center;
    font-size: 14pt;
    font-weight: 600;
    background-color: #ffc266;
    border-radius: 10px;
  }
</style>
