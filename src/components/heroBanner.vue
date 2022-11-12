<template>
    <div>
        <b-card img-src=./images/izrul.png img-left class="heroCont mx-auto" style="margin-top: 10%; padding: 30px; padding-bottom: 0px">
          <b-card-text class="mt-5">
            <h1 class="my-5">Izrulfizal Saufihamizal</h1>
            <hr>
            <Transition mode="out-in">
              <h3 class="my-5" ref="positionPara" :key="position">{{ position }}</h3>
            </Transition>
          </b-card-text>  
        </b-card>
    </div>
  </template>
  
  <script>
  export default {
    name: 'heroBanner',
    data(){
      return{
        options: ["Software Engineer", "Code Enthusiast", "Speaker", "Occasional Perfectionist"],
        position: "Software Engineer",
      }
    },
    async mounted(){
      const timer = ms => new Promise(res => setTimeout(res, ms))

      for (var i = 0; i < this.options.length; i++) {
        this.position = this.options[i]
        await timer(1500)
        if(i === this.options.length - 1) {
          i=-1 
          continue
        }
      }
    },
    methods:{
      changePosition(i){
        setTimeout(() => { console.log(this.options[i]) }, 1000);
      },  
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
  .heroCont{
    background-color: #B8BEE3;
  }
  </style>
  <style>
.v-enter-active,
.v-leave-active {
  transition: opacity 0.5s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}
</style>
  