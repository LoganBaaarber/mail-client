<template>
  <div class="main">
    <h1>Join The Mailing List</h1>

    <h3>Signup</h3>
    <form @submit.prevent="postUser">
      <label>First Name
      <input type="text" class="form-control" v-model="postFirstName"/>
    </label>
      <label>Last Name
      <input type="text" class="form-control" v-model="postLastName"/>
    </label>
      <label>Email
      <input type="text" class="form-control" v-model="postEmail"/>
    </label>
      <button type="submit" class="btn btn-primary">Submit</button>
    </form>
    
  </div>
</template>

<script>
import axios from 'axios';
import Vue from 'vue';



export default {
  name: 'JoinList',
  data() {
    return {
      postFirstName: '',
      postEmail: '',
      postLastName: '',
      errors: []
    }
  },
  methods: {
  postUser() {
    axios.post(`http://localhost:3000/register`, {
      first_name: this.postFirstName,
      email: this.postEmail,
      last_name: this.postLastName
    })
    .then(response => {
      console.log(response);
      if(response.data.status == "error") {
        Vue.toast("The form isn't filled out!");
      } else {
      Vue.toast('Registered for the mailing list!');
      }
    })
    .catch(e => {
      //this.errors.push(e)
      Vue.toast("Ooops! " + e);
    })
  }
 }
}
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
