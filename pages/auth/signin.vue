<template>
  <div class="d-flex align-items-center justify-content-center flex-column main px-2">
    <h4>මේකෙන් යන්න පුළුවන් පාස්වර්ඩ් දන්න අයට විතරයි </h4>
    <form>
      <!-- Email input -->
      <div class="form-outline mb-4">
        <input
          type="email"
          id="form2Example1"
          class="form-control"
          v-model="auth.email"
          placeholder="Email"
        />
        <label class="form-label" for="form2Example1" >Email</label>
      </div>
      <!-- Password input -->
      <div class="form-outline mb-4">
        <input
          type="password"
          id="form2Example2"
          class="form-control"
          v-model="auth.password"
          placeholder="Password"
        />
        <label class="form-label" for="form2Example2">Password</label>
      </div>
      <!-- Submit button -->
      <button type="button" @click="login" class="btn btn-primary btn-block mb-4">
        Sign in
      </button>
    </form>
  </div>
</template>

<style scoped>
.main {
  height:92vh;
}
form {
  width: 300px;
  border: 1px solid #777;
  padding: 30px;
  background: #eee777;
  margin-top:50px;
}
</style>

<script>
export default {
  ///////////////////////////////
  data() {
    return {
      auth: {
        email: '',
        password: '',
      },
    }
  },
////////////////////////////////////////////
  methods:{
    login() {
      this.$fire.auth.signInWithEmailAndPassword(this.auth.email, this.auth.password)
      .catch(function (error) {
        alert(error.message)
      }).then((user) => {
        this.$router.go('/secret')
      })
    }
  },
  ////////////////////////////////////////////
  layout:'main'
}
</script>