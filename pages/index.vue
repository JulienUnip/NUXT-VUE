
<template>
  <div>
    <h1>Events</h1>

    <div v-for="(value) in titles" :key="value">
      {{ value.title }}
    </div>

  </div>
</template>

<script>
  import axios from 'axios'

  export default {
    asyncData ({ params }) {
      return axios.get(`https://jsonplaceholder.typicode.com/todos/`)
      .then((res) => {
        console.log(res)
        return { titles: res.data }
      })
    }
  }
</script>