<template>
  <div id="app">
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

</style>
