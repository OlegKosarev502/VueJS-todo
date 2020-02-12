<template>
  <div id="app">
    <div class="app-nav">
      <div class="nav-item active-item">
        <router-link class="nav-link" to="/">Home</router-link>
      </div>
      <div class="nav-item">
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
  padding-left: 10px;
  display: flex;
  align-items: center;
  border-radius: 5px;
}

.active-item {
  background-color: #3f4d71;
}
.active-item .nav-link {
  color: white;
}

.nav-link {
  width: 100%;
  height: 30px;
  font-size: 20px;
  line-height: 30px;
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
