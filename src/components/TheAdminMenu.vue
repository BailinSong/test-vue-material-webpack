<template>

    <Menu active-name="1-2" theme="dark" width="auto" :class="menuitemClasses">
      <MenuItem name="1-1" >

        <router-link to="Server"><Icon type="ios-navigate"></Icon>
          <span>Server</span></router-link>
      </MenuItem>
      <MenuItem name="1-2">
        <Icon type="search"></Icon>
        <span>Option 2</span>
      </MenuItem>
      <MenuItem name="1-3">
        <Icon type="settings"></Icon>
        <span>Option 3</span>
      </MenuItem>
    </Menu>


</template>

<script>
  export default {
    name: "TheAdminMenu",
    computed: {
      menuitemClasses: function () {
        return [
          'menu-item',
          this.isCollapsed ? 'collapsed-menu' : ''
        ]
      }
    }
  }
</script>

<style scoped>
  .menu-item span {
    display: inline-block;
    overflow: hidden;
    width: 69px;
    text-overflow: ellipsis;
    white-space: nowrap;
    vertical-align: bottom;
    transition: width .2s ease .2s;
  }

  .menu-item i {
    transform: translateX(0px);
    transition: font-size .2s ease, transform .2s ease;
    vertical-align: middle;
    font-size: 16px;
  }


</style>
