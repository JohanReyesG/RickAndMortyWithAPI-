<template>
  <div id="app">
    <div id="nav">
      <!-- Image and text -->
      <nav class="navbar navbar-light bg-light">
        <div class="container-fluid " >
          <a class="navbar-brand" href="#">
           
            Rick <span>And</span> Morty
          </a>
        </div>
      </nav>
    </div>
    <router-view />
  </div>
</template>

<style lang="scss">
@font-face {
  font-family: get_schwifty;
  src: url('./assets/get_schwifty.ttf');
}
.navbar{
  background: url('./assets/stars.png');
  background-repeat: 0 0;
   min-height: 100%;
  background-color: #0f1c23!important;
}
.navbar-brand {
  z-index: 99999;
  padding-left: 10px;
  font-family: get_schwifty;
  color: #53a6c1 !important;
  font-size: 2rem;
  text-shadow: 3px 3px 0 #d3da49, 3px -3px 0 #d3da49, -3px 3px 0 #d3da49,
    -3px -3px 0 #d3da49, 3px 0px 0 #d3da49, 0px 3px 0 #d3da49,
    -3px 0px 0 #d3da49, 0px -3px 0 #d3da49,
    2px 2px 15px rgb(136, 255, 0),
    -3px -3px 15px rgb(136, 255, 0);
}



.navbar-brand::before{
  content: 'Rick And Morty';
   font-family: get_schwifty;
   position:absolute;
  color: #53a6c1!important;
 text-shadow: 1px 1px 0 #000, 1px -1px 0 #000, -1px 1px 0 #000,
    -1px -1px 0 #000, 1px 0px 0 #000, 0px 1px 0 #000,
    -1px 0px 0 #000, 0px -1px 0 #000;

}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}

</style>
