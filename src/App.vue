<template>
  <div id="app">
    <md-toolbar color="primary" class="expanded-toolbar">
      <span class="branding">
        <md-button><router-link to="home">{{title}}</router-link></md-button>
        <md-button><router-link to="home"><md-icon>home</md-icon></router-link></md-button>
      </span>
      <md-button v-if='authenticated' v-on:click='logout' id='logout-button'>Logout</md-button>
      <md-button v-else v-on:click='login' id='login-button'>Login</md-button>
      <md-menu md-direction="bottom-start">
        <md-button md-menu-trigger>
          <md-icon>menu</md-icon>
        </md-button>
        <md-menu-content>
          <md-menu-item @click="$router.safeNavigate($route, 'home')">Home</md-menu-item>
          <md-menu-item @click="$router.safeNavigate($route, 'read')">Read</md-menu-item>
        </md-menu-content>
      </md-menu>
    </md-toolbar>
    <div class="router">
      <router-view/>
    </div>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
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
  margin-top: 60px;
}
</style>
