<template>
  <div id="app">
    <div class="app-nav">
      <div 
        class="nav-item"
        v-bind:class="{ 'active-nav-item' : currentPage === 'home' }"
        v-on:click="toggleActive('home')"
      >
        <router-link class="nav-link" to="/">Home</router-link>
      </div>
      <div
        class="nav-item"
        v-bind:class="{ 'active-nav-item' : currentPage === 'todos' }"
        v-on:click="toggleActive('todos')"
      >
        <router-link class="nav-link" to="/todos">Todos</router-link>
      </div>
    </div>

    <div class="app-main">
      <div class="app-header">
        <h1>Todo application</h1>
      </div>

      <div class="app-views">
        <router-view />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      currentPage: 'home'
    }
  },
  methods: {
    toggleActive(page) {
      this.currentPage = page
    }
  }
}
</script>

<style>
body {
  padding: 0;
  margin: 0;
  min-height: 100vh;
}

#app {
  display: flex;
  align-items: stretch;
  min-height: 100vh;
}

.app-nav {
  flex-basis: 12.5%;
}

.nav-item {
  height: 40px;
  margin: 5px 15px;
  display: flex;
  align-items: center;
  border-radius: 5px;
}

.nav-item:hover .nav-link {
  color: #55ae95;
}

.active-nav-item {
  background-color: #3f4d71;
}
.active-nav-item .nav-link,
.active-nav-item:hover .nav-link {
  color: white;
}

.nav-link {
  width: 100%;
  height: 100%;
  padding-left: 10px;
  font-size: 20px;
  line-height: 40px;
  color: #3f4d71;
  text-decoration: none;
}

.app-main {
  box-sizing: border-box;
  flex-basis: 87.5%;
  border-left: 1px solid #3f4d71;
}

.app-header {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 50px;
  background-color: #55ae95;
}

.app-header h1 {
  margin: 0;
  color: #fff;
}
</style>
