<template>
  <div class="Home">
    <div class="toviText">
      What is <img src="./assets/tovi.png"><br>eating for lunch?
    </div>
    <div class="tellUs" v-on:click="tellUs">
      Tell us!
    </div>
  </div>
</template>

<script>

export default{
  name: 'Home',
  methods:{
    tellUs(){
     this.$parent.$options.methods.processTellus();
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
 .toviText{
   color: rgba(0,0,0,.6);
   background-color: #fff;
   text-shadow: rgba(0,0,0,.2) 2px 6px 5px,rgba(255,255,255,.4) 0 -4px 30px;
   font-size: 45px;
   padding: 30px;
 }
 .tellUs{
   padding: 20px;
   border: 3px solid green;
   margin: 20px;
   background: ghostwhite;
   font-size: 25px;
   width: 215px;
   border-radius: 20px;
   cursor: pointer;
   text-transform: uppercase;
   text-align: center;
 }
 .tellUs:hover{
   background: white;
   border: 2px solid green;
 }
</style>
