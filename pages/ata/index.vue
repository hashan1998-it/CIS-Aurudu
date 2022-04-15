<template>
  <div class="main"> 
    <div
      class="justify-content-center align-items-center flex-column counter"
      :style="mainStyle"
    >
      <h2>ඇට ගාන හංගලා තියෙන්නේ</h2>
      <h2>තප්පර {{ time }} ක් ඉන්න</h2>
    </div>

    <div class="align-items-center justify-content-center flex-column form" :style="formstyle" >
      <div class="content d-flex align-items-center justify-content-center flex-column">
        <h2 class="pb-3">මේක පුරවන්න.</h2>
        <input type="text" v-model="name" class="mt-5 form-control" :style="{border: showNull ? 'red 1px solid !important' : 'black'}"/>
        <label for="name">නම</label>
        <input type="text" v-model="count" class="form-control" :style="{border: showNull ? 'red 1px solid !important' : 'black'}"/>
        <label for="name">ඇට ගාන </label>
        <button @click="log" class="btn btn-primary mt-3"> හරි </button>
        <h4 v-show='showNull' class="pt-5">පුරවලා නැ </h4>
      </div>
    </div>
  </div>
</template>

<script>
const axios = require('axios').default;
export default {
  
  created() {
    var timeint = setInterval(() => {
      this.time -= 1
      this.colorCode += 1
      if (this.time == 0) {
        this.showCounter = false
      }
      if (this.time == 0) {
        clearInterval(timeint)
      }
    }, 1000)
  },
  data() {
    return {
      time: '10',
      colorCode: 1,
      showCounter: true,
      name: '',
      count: '',
      showNull:false,
    }
  },
  computed: {
    mainStyle() {
      return {
        background: 'rgba(255,0,0,0.' + this.colorCode + ')',
        display: this.showCounter ? 'flex' : 'none',
      }
    },
    formstyle() {
      return{
        display: this.time !==0 ? 'none' : 'flex'
      }
    }
    
  },

  layout: 'main',

  methods: {
    log() {
      axios
        .post('https://papaya-auth-default-rtdb.firebaseio.com/post.json', {
          name: this.name,
          count: this.count
        })
        .then(function (response) {
          console.log(response)
        })
         if(this.name === "" || this.count=== "")
         {
           this.showNull =true;

         }
         else{
           this.$router.push('/sucess')
         }


    },
  },
}
</script>

<style scoped>
.counter {
  height: 100vh;
  transition: all ease-in 0.5s;
}
.counter h2 {
  font-size: 48px;
  font-weight: 700;
}
.form{
  height: 100vh;
  background:rgba(0,0,0,0.5)
}
.form h2 {
  font-weight: 700;
}
.content{
  border: 1px solid #777;
  padding:60px;
  background:#eee;
}
.content label {
  padding-bottom: 10px;
}
.content input {
  margin-top: 10px;
}
.content button{
  width:110px;
}
@media screen and (max-width: 530px) {
  .counter h2 {
    font-size: 28px;
  }
}
.formStyle{
   background: 'rgba(0,0,0,0.5)';
   display: 'none'   
 }
 .content h4{
   color:red;
 }
</style>
