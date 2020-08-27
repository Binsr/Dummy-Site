<template>
  <div id="app">
      <div id="curtain" class="curtain-component">
        <img src="@/assets/logo.png" id="logo">
      </div>
      <!-- <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link> -->
    <router-view/>
  </div>
</template>
<script>
export default {
  data(){
    return{
      curtainTop: 0,
      logoTop: 280
    }
  },
  mounted: function() {
      console.log(document.getElementById("curtain").offsetTop);
      window.addEventListener('scroll', this.moveCurtain); 
  },

  methods: {
    moveCurtain: function(){
        if(-this.curtainTop > 500) return;
        this.curtainTop-= 35;
        window.scrollTo(0, 0);
        
        document.getElementById("curtain").style.top= this.curtainTop + "px";
        document.getElementById("logo").style.top= -this.curtainTop/2 + this.logoTop + "px";
        console.log("pozvan" + this.curtainTop);
    }
  }
}
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#logo{
  position: absolute;
  top: 280px;
  width: 150px;
  height: 150px;
  left: 44%;
}

.curtain-component{
  width: 100%;
  display: flex;
  position: fixed;
  top: 0;
  background-color: #e31717e6;
  height: 700px; 
}
#app{
  padding: 0;
}

body,html{
  padding: 0 !important;
  margin: 0 !important;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
