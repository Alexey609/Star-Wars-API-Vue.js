<template>
  <div id="nav">
    <router-link to="/">Домашняя</router-link> |
    <router-link to="/about">Статистика вселенной</router-link> |
    <router-link to="/planets">Планеты</router-link>
  </div>
  <router-view/>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: goldenrod;
}
</style>
