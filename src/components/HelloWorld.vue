<template>
  <div class="hello">
    <ul></ul>
    <h3>Ecosystem</h3>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  async mounted() {
    let response;
    try {
      response = axios.get("https://api.23andme.com/authorize/", {
        redirect_uri: "http://localhost:5000/receive_code/",
        client_id: "8ed0f4f6c6b852062fa8b941b7548e4a",
        client_secret: "13673a21234bf2d1e6ec8fbb07f4679c",
        response_type: "code",
        scope: "genomes"
      });
    } catch (error) {
      console.log("error", error);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
