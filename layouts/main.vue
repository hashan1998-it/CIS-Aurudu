<template>
  <div class="main conatiner-fluid">
    <nav class="navbar navbar-expand-md navbar-light">
      <nuxt-link to="/" class="navbar-brand" href="#">CIS අවුරුදු</nuxt-link>
      <button
        class="navbar-toggler"
        type="button"
        data-toggle="collapse"
        data-target="#navbarNavAltMarkup"
        aria-controls="navbarNavAltMarkup"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
        <div class="navbar-nav ml-auto ">
          <nuxt-link to="/games" class="nav-item nav-link active px-5" href="#" >Games<span class="sr-only">(current)</span></nuxt-link>
          <nuxt-link to="/auth/signin" class="nav-item nav-link active px-5" href="#" v-show="!$nuxt.$fire.auth.currentUser" >Log in<span class="sr-only">(current)</span></nuxt-link>
          <nuxt-link to="/secret" class="nav-item nav-link active px-5" href="#" v-show="$nuxt.$fire.auth.currentUser">Authorized<span class="sr-only">(current)</span></nuxt-link>
        </div>
      </div>
    </nav>
    <Nuxt/>
  </div>
</template>

<style scoped>
.navbar{
  background-color: #777;
}
.navbar-brand,.nav-item{
  color: #fff !important;
}
.navbar-brand{
  font-weight: 600;
}

</style>

