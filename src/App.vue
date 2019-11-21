<template>
  <div id="app">
    <div class="app-nav">
      <div class="nav-item">
        <router-link to="/">Home</router-link>
      </div>
      <div class="nav-item">
        <router-link to="/todos">Todos</router-link>
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

<style>
@import url("https://fonts.googleapis.com/css?family=Amatic+SC|Crimson+Text&display=swap");

body {
  padding: 0;
  margin: 0;
  min-height: 100vh;
  font-family: "Crimson Text", serif;
}

#app {
  display: flex;
  align-items: stretch;
  min-height: 100vh;
  background-color: #faf9f8;
}

.app-nav {
  flex-basis: 12.5%;
}

.nav-item {
  height: 40px;
  text-align: center;
}

.nav-item:hover {
  background-color: #3f4d71;
}

.nav-item a {
  font-size: 24px;
  color: #3f4d71;
}

.nav-item:hover a {
  color: #fff;
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
  height: 15vh;
  background-color: #55ae95;
}

.app-header h1 {
  margin: 0;
  font-size: 48px;
  color: #fff;
}
</style>
