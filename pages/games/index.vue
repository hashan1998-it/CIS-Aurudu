<template>
  <div class="main">
    <h1 class="fw-light text-center text-lg-start mt-4 mb-0">ගේම්ස් ටික</h1>

    <hr class="mt-2 mb-5" />
    <div class="flex-container row" style="textDecoration: none;">
      <nuxt-link to="/ata" style="textDecoration: none;" class="p-5">
        <div class="card" style="width: 18rem">
          <img
            class="card-img-top"
            src="@/static/papaya.jpg"
            alt="Card image cap"
          />
          <div class="card-body">
            <p class="card-text" style="textDecoration: none;">
              ගස්ලබු ගෙඩියේ ඇට ගණන් කිරීම
            </p>
          </div>
        </div>
      </nuxt-link>

      <nuxt-link to="/gallery" style="textDecoration: none" class="p-5">
        <div class="card" style="width: 18rem">
          <img
            class="card-img-top"
            src="@/static/smile.png"
            alt="Card image cap"
            style="width: 286px; height: 286px"
          />
          <div class="card-body">
            <p class="card-text" style="textdecoration: none">ආතල්ම photo එක</p>
          </div>
        </div>
      </nuxt-link>
    </div>
  </div>
</template>

<script>
export default {
  layout: 'main',
}
</script>

<style scoped>
p,
nuxt-link,
.card-text {
  color: red;
  text-decoration: none !important;
  font-size: 1.1rem;
  font-weight:700;
}
@media screen and (max-width: 993px) {
  .flex-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }
}
.card:hover{
  background:yellow;
}
</style>
