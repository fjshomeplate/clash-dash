<template>
  <div class="hello">
    <input v-model="tag" />
    <button @click="fetch(tag)">Fetch</button>
    <h3>{{info}}</h3>
  </div>
</template>

<script>
import axios from "axios"
export default {
  name: 'Dashboard',
  data() {
    return {
      info : null,
      tag: ""
    }
  },
  methods: {
    fetch(tag) {
      axios.get("http://localhost:8081/clash/"+tag)
        .then(data=> {this.info = data.data})
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
p {
  margin: 40px 0 0;
}
a {
  color: #42b983;
}
</style>
