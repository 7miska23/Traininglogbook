<template>
<div>
  <div class="row">
    <div class="col">
      <h1 class="text-center mb-5">This is a login page</h1>
    </div>
  </div>
  <div class="row">
    <div class="col"></div>
    <div class="col">
      <form @submit.prevent="signup">
        <div class="form-group">
          <label for="emailField">Email address</label>
          <input v-model="email" type="email" class="form-control" id="emailField" aria-describedby="emailHelp" placeholder="Enter email">
          <small id="emailHelp" class="form-text text-muted">We'll never share your email with anyone else.</small>
        </div>
        <div class="form-group">
          <label for="passwordField">Password</label>
          <input v-model="password" type="password" class="form-control" id="passwordField" placeholder="Password">
        </div>
        <button type="submit" class="btn btn-primary mt-5">Submit</button>
      </form>
    </div>
    <div class="col"></div>
  </div>
</div>
</template>

<script>
import firebase from 'firebase'
export default {
  data () {
    return {
      email: '',
      password: ''
    }
  },
  methods: {
    signup () {
      firebase.auth().signInWithEmailAndPassword(this.email, this.password).catch(function(error) {
        console.log(error);
      });
    }
  }
}
</script>