<template>
  <div id="app">
    <md-app md-waterfall md-mode="fixed">
      <md-app-toolbar class="md-primary">
        <router-link to="/"><span class="md-title">TCP代理</span></router-link>
      </md-app-toolbar>
      <md-app-drawer md-permanent="clipped">
        <md-list >
          <md-list-item to="/Server">ServerAdd</md-list-item>
          <md-list-item>Sent Mail</md-list-item>
          <md-list-item>Trash</md-list-item>
          <md-list-item>Spam</md-list-item>
        </md-list>
      </md-app-drawer>
      <md-app-content>
        <router-view/>
      </md-app-content>
    </md-app>

  </div>
</template>

<script>
  export default {
    name: 'App'
  }
</script>

<style lang="scss">
  /*@import "~vue-material/dist/theme/engine";
  @include md-register-theme("default", (
    default: md-get-palette-color(black, A200),
    primary: md-get-palette-color(blue, A200), // The primary color of your application
    accent: md-get-palette-color(red, A200), // The accent or secondary color
         theme: dark
   ));*/


  /*#app {*/
  /*font-family: 'Avenir', Helvetica, Arial, sans-serif;*/
  /*-webkit-font-smoothing: antialiased;*/
  /*-moz-osx-font-smoothing: grayscale;*/
  /*text-align: center;*/
  /*color: #2c3e50;*/
  /*margin-top: 60px;*/
  /*}*/
  .md-app-drawer {
    /*background: #323232;*/
    width: 200px;
    height: 600px;
    max-height: 100%;
    max-width: 100%;
    /*display: inline-block;*/
    /*vertical-align: top;*/
    /*border: 1px solid rgba(#000, .12);*/
  }

</style>
