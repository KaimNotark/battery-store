<template>
  <div id="app">
    <div id="wrapper" class="wrapper">

      <Header class="header" @is-briefly-flag="brieflyDetailed"></Header>

      <div class="container__sidebar-main">
        <aside class="aside">
          <Sidebar class="sidebar" />
        </aside>
        <Main class="main" />
      </div>

      <vFooter></vFooter>
    </div>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";
import Sidebar from "./components/Sidebar.vue";
import vFooter from "./components/vFooter.vue";

export default {
  name: "app",
  components: {
    Header,
    Main,
    Sidebar,
    vFooter
  },

  data: () => ({
    isBriefly: true,
    isDetailed: false
  }),

  methods: {
    brieflyDetailed: function(isBriefly, isDetailed) {
      this.isBriefly = isBriefly;
      this.isDetailed = isDetailed;
    }
  }
};
</script>

<style lang="scss">
@import "./stylesheets/variables.scss";
@import "./stylesheets/resets.scss";

#app {
  width: 1140px;
  margin: 0 auto;

  html {
    scroll-behavior: smooth;
  }

  .wrapper *,
  .wrapper *::before,
  .wrapper *::after {
    box-sizing: border-box;
  }

  .wrapper {
    max-width: 1100px;
    margin: 0 auto;
    margin-left: 20px;
    margin-right: 20px;
  }

  body {
    min-height: 100vh;
    font-family: $font-family-primary;
    box-sizing: border-box;
  }

  .container__sidebar-main {
    display: flex;
    justify-content: space-between;
  }

  .sidebar {
    display: block;
    margin-top: 10px;
  }
  .main {
    display: block;
  }
}
</style>
