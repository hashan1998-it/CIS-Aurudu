<template>
  <div class="d-flex align-items-center justify-content-center flex-column vh-100">
    <div class="card w-50 text-center">
      <div class="card-body">
        <h5 class="card-title">ඇට ගාන </h5>
        <hr class="mt-2 mb-5">
        <p class="card-text">
          592
        </p>
        <nuxt-link to="/auth/signout"><button class="btn btn-primary">Sign Out</button></nuxt-link>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  layout: 'main',
}
</script>

<style scoped>
.card{
    background-color:#eee
}
.card-text{
    font-size:5rem;
    font-weight: 700;
}
.card-title{
    color:red;
    font-weight: 600;
    
}
</style>
