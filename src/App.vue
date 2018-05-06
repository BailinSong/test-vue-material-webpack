<template>
  <div id="app">
<<<<<<< HEAD
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
=======
    <Layout style="height: 100%">
      <Header class="layout-header-bar" theme="dark">
        <div class="layout-logo"><h1>Admin</h1></div>
      </Header>
      <Layout>
        <Sider breakpoint="md" collapsible :collapsed-width="78" v-model="isCollapsed">
          <TheAdminMenu/>
          <div slot="trigger"></div>
        </Sider>
        <Content :style="{margin: '20px',  minHeight: '220px'}">
          <router-view/>
        </Content>
      </Layout>

    </Layout>
>>>>>>> 更新进度

  </div>
</template>

<script>
  import TheAdminMenu from './components/TheAdminMenu'

  export default {
    name: 'App',
    components: {
      TheAdminMenu: TheAdminMenu
    },
    data() {
      return {
        isCollapsed: false
      };
    }


  }
</script>

<<<<<<< HEAD
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

=======
<style scoped>
  .layout-logo{
    color: azure;
    border-radius: 3px;
    float: left;
    position: relative;
    /*top: 0px;*/
    /*left: 5px;*/
  }

  .layout-header-bar {
    box-shadow: 0 1px 1px rgba(0, 0, 0, .1);
  }

  .collapsed-menu span {
    width: 0px;
    transition: width .2s ease;
  }

  .collapsed-menu i {
    transform: translateX(5px);
    transition: font-size .2s ease .2s, transform .2s ease .2s;
    vertical-align: middle;
    font-size: 22px;
  }

>>>>>>> 更新进度
</style>
