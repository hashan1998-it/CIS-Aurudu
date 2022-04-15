<template>
  <div
    class="landing-page d-flex justify-content-center align-items-center flex-column"
  >
    <h1>CIS අවුරුදු</h1>
    <p>V 1.0</p>
    <nuxt-link to="/games"
      ><button class="btn btn-secondary">ගිහින් බලමු</button></nuxt-link
    >
  </div>
</template>

<script>
export default {
  layout: 'main',
}
</script>

<style scoped>
.landing-page {
  height: 100vh;
  background-image: url('../static/background.png');
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
}
.landing-page h1 {
  font-size: 5rem;
  font-weight: 700;
  color: rgb(247, 247, 247);
}
.landing-page p {
  font-weight: 300;
  font-size: 2rem;
  padding-top: 10px;
  color: #fff;
}
.landing-page button {
  margin-top: 10px;
  padding: 8px;
  width: 110px;
  border-radius: 3px;
}
@media screen and (max-width: 335px) {
    .landing-page h1 {
    font-size: 48px;
  }
}
</style>
