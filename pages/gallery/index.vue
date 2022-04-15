<template>
   <div class="container">

  <h1 class="fw-light text-center text-lg-start mt-4 mb-0">Photo ටික </h1>

  <hr class="mt-2 mb-5">

  <div class="row text-center text-lg-start">
    <div class="col-lg-3 col-md-4 col-6" v-for="(photo,index) in photos" :key="index">
      <a href="#" class="d-block mb-4 h-100">
        <img class="img-fluid img-thumbnail" :src="photo.URL" alt="">
      </a>
    </div> 
  </div>

  <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-ka7Sk0Gln4gmtz2MlQnikT1wXgYsOg+OMhuP+IlRH9sENBO0LRn5q+8nbTov4+1p" crossorigin="anonymous"></script>

</div>
</template>

<script>
import data from'~/Photo.json'
export default {
    layout:'main',
    components: {

    },
    data: () => ({
       photos:data,
       count:''
    }),
    created(){
     console.log(data[1].URL);
    
    },
    methods:{
      
    }
}
</script>