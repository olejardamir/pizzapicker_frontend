<template>
  <div id="chef">
    <div class="question" style="display: block">
      <img src="./assets/chefq.png" width="500">
    </div>
    <div class="answer" style="display: none">
      <img src="./assets/chef.png" width="500">
    </div>
  </div>
  <div id="menu">
    <div class="title">
      {{ title }}
    </div>
    <div class="box">
      <div id="header">
        <div id="leftIcon" class="left-align headerFont">
          <img src="./assets/leftIcon.png" width="25"> 3
        </div>
        <div id="logo" class="center-align">
          <img src="./assets/logo.png" height="50">
        </div>
        <div id="rightIcon" class="right-align headerFont">
          <img src="./assets/rightIcon.png" width="25"> {{increment}}
        </div>
      </div>
      <div class="content">
        <div id="homeComponent" style="display: block"><Home/></div>
        <div id="newResultComponent" style="display:none;"><NewResult/></div>
        <div id="emptyResultComponent" style="display:none;"><EmptyResult/></div>
      </div>
      <div>
        <div id="mainButtons">
          <div id="leftButton" class="pickerBgr" v-on:click="processPicker">
            <div class="buttonFont">
              Picker</div></div>
          <div id="rightButton" class="resultsBgr" v-on:click="processResults">
            <div class="buttonFont">
              Results</div></div>
        </div>
      </div>
    </div>
  </div>

</template>

<script>
import Home from "./components/Home.vue";
import NewResult from "./components/NewResult.vue";
import EmptyResult from "./components/EmptyResult.vue";

export default {
  name: 'Pizza Picker',
  components: {
    Home,
    NewResult,
    EmptyResult
  },
  data: function () {
    return {
      title: "Home",
      increment: 4
    };
  },
  methods:{

    processPicker(){
      this.title = "Home";
      document.getElementsByClassName('pickerBgr')[0].style.background = "white";
      document.getElementsByClassName('resultsBgr')[0].style.background = "gray";
      document.getElementsByClassName('question')[0].style.display = "block";
      document.getElementsByClassName('answer')[0].style.display = "none";
      this.displayComponent("homeComponent");
    },
    processResults(){
      this.title = "Empty Result";
      this.increment = this.increment+1;
      document.getElementsByClassName('pickerBgr')[0].style.background = "gray";
      document.getElementsByClassName('resultsBgr')[0].style.background = "white";
      document.getElementsByClassName('question')[0].style.display = "none";
      document.getElementsByClassName('answer')[0].style.display = "block";
      this.displayComponent("emptyResultComponent");
    },
    processTellus(){
      this.title = "New Result";
      document.getElementsByClassName('question')[0].style.display = "none";
      document.getElementsByClassName('answer')[0].style.display = "block";
      this.displayComponent("newResultComponent");
    },
    displayComponent(componentName){
      document.getElementById("homeComponent").style.display = "none";
      document.getElementById("newResultComponent").style.display = "none";
      document.getElementById("emptyResultComponent").style.display = "none";
      document.getElementById(componentName).style.display = "block";

    },
  }
}
</script>

<style>

body {
  background-image: url("./assets/background.jpg");
  background-size: cover;
  background-repeat: no-repeat;
}

/*------------MAIN------------------*/
#menu{
  margin: 0;
  position: absolute;
  left: 38%;
  top: 10%;
}
.title{
  color: #333333;
  background: #FFFFFF;
  text-shadow: 2px 2px 0px #FFFFFF, 5px 4px 0px rgba(0,0,0,0.15);
  font-size: 25px;
  padding: 10px;
  background: rgba(255,255,255,0.8);
  border-radius: 20px 20px 0 0;
}



/*------------HEADER------------------*/
#header{
}
#leftIcon{
}
#logo{
}
#rightIcon{
  float: left;
}

.box{
  width: 500px;
  height: 70px;
  position: relative;
  border: 3px solid green;
  background: rgb(0,147,68);
  background: linear-gradient(90deg, rgba(0,147,68,1) 0%,
  rgba(255,255,255,1) 25%, rgba(255,255,255,1) 51%, rgba(255,255,255,1) 75%, rgba(207,39,52,1) 100%);
}
.left-align {
  margin: 0;
  position: absolute;
  left: 4%;
  top: 16%;
}
.center-align {
  margin: 0;
  position: absolute;
  top: 12%;
  left: 35%;
}
.right-align {
  margin: 0;
  position: absolute;
  right: 4%;
  top: 25%;
}
.headerFont{
  color: #FFFFFF;
  text-shadow: 1px 0 0 #626262, 0 -1px 0 #626262, 0 1px 0 #626262, -1px 0 0 #626262;
  font-weight: bold;
}


/*------------CONTENT------------------*/
.content{
  position: relative;
  border: 3px solid green;
  top: 110%;
  width: 500px;
  height: 329px;
  margin: -3px;
  background: #fff;
}

/*------------BUTTONS------------------*/
#mainButtons{
  position: relative;
  border: 3px solid green;
  top: 81px;
  width: 500px;
  height: 65px;
  margin: -3px;
  border-radius: 0px 0px 20px 20px;
}
#leftButton{
  position: relative;
  border: 3px solid green;
  top: 0px;
  width: 247px;
  height: 65px;
  margin: -2px;
  border-radius: 0px 0px 0px 20px;
  text-transform: uppercase;
}
#rightButton{
  position: absolute;
  border: 3px solid green;
  top: 0px;
  right: 0px;
  width: 251px;
  height: 65px;
  margin: -2px;
  border-radius: 0px 0px 20px 0px;
  text-transform: uppercase;
}
.buttonFont{
  font-family: verdana;
  text-align: center;
  font-size: 35px;
  color: rgb(96, 96, 96);
  background-color: rgba(84, 84, 84, 0);
  text-shadow: rgb(214, 214, 214) 2px 2px 2px;
  padding-top: 14px;
}
.resultsBgr{
  background: gray;
  cursor: pointer;
}
.pickerBgr{
  background: white;
  cursor: pointer;
}

</style>
