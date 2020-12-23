<template>
  <div class="newResult">

    <div class="slice">
      <img src="./assets/slice.png" width="200">
    </div>
    <div class="plate">
      <img src="./assets/plate.png" width="250">
    </div>
    <div class="pizzatext">It's Pizza!</div>

  </div>
</template>

<script>

export default{
  name: 'New Result',
  methods:{

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
.slice{
  position: absolute;
  z-index: 1;
  margin-left: 31%;
}
.plate{
  text-align: center;
  position: absolute;
  margin-left: 25%;
  margin-top: 75px;
}
.pizzatext{
  position: absolute;
  margin-left: 28%;
  font-size: 35px;
  margin-top: 245px;
  font-weight: bold;
  color: #fff;
  text-shadow: -1px 0 black, 0 1px black, 1px 0 black, 0 -1px black;
  text-transform: uppercase;
}
</style>
