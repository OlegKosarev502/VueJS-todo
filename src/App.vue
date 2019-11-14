<template>
  <div id="app">
    <div class="app-header">
      <h1>
        Todo application
      </h1>
    </div>
    <div class="app-body">
      <div class="app-nav">
        <div class="nav-item">
          <router-link to="/">Home</router-link>
        </div>
        <div class="nav-item">
          <router-link to="/todos">Todos</router-link>
        </div>
      </div>
      <div class="view-container">
        <router-view />
      </div>
    </div>
  </div>
</template>

<style>
  @import url('https://fonts.googleapis.com/css?family=Amatic+SC|Crimson+Text&display=swap');

  body {
    padding: 0;
    margin: 0;
    min-height: 100vh;
    font-family: 'Crimson Text', serif;
  }

  #app {
    min-height: 100%;
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

  .app-body {
    display: flex;
    align-items: stretch;
    min-height: 85vh;
    background-color: #faf9f8;
  }

  .app-nav {
    flex-basis: 15%;
    border-right: 1px solid #3f4d71;
  }

  .nav-item {
    box-sizing: border-box;
    height: 40px;
    padding-left: 15px;
  }

  .nav-item:hover {
    background-color: #3f4d71;
  }

  .nav-item:hover a {
    color: #fff;
  }

  .nav-item a {
    font-size: 24px;
    color: #3f4d71;
  }

  .view-container {
    box-sizing: border-box;
    flex-basis: 85%;
    padding: 20px 40px;
  }
</style>
