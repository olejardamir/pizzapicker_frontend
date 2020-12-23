<template>
  <div class="emptyResult">

    <div class="text tipSize">
      Tip:
    </div>
    <div class="text textSize">
      It's always Pizza.
    </div>
  </div>
</template>

<script>

export default{
  name: 'Empty Result',
  methods:{

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
.text{
  color: rgba(0,0,0,.6);
  background-color: #fff;
  text-shadow: rgba(0,0,0,.2) 2px 6px 5px,rgba(255,255,255,.4) 0 -4px 30px;
  padding: 30px;
}
.tipSize{
  font-size: 15px;
}
.textSize{
  font-size: 30px;
}
</style>
