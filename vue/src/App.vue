<template>
  <div id="app">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Lato&family=Poppins:wght@300&display=swap" rel="stylesheet">
    <div id="nav">
      <router-link v-bind:to="{ name: 'home' }">Home</router-link>&nbsp;|&nbsp;
      <router-link v-bind:to="{name: 'areas'}">Areas</router-link>&nbsp;|&nbsp;
      <router-link v-bind:to="{name: 'climbing-log', params: {userId: $store.state.user.id}}">MyClimbs</router-link>&nbsp;|&nbsp;
      <router-link v-bind:to="{name: 'search'}">Find Routes</router-link>&nbsp;|&nbsp;
      <router-link v-bind:to="{ name: 'logout' }" v-if="$store.state.token != ''">Logout</router-link>
      <router-link v-bind:to="{ name: 'login' }" v-if="$store.state.token == ''">Login</router-link>
    </div>
    <router-view class="contents" />
    <footer>
      <p id="footer-text">The New River Gorge Climbing Guide</p>
    </footer>
  </div>
</template>

<style>

#app {
  position: relative;
  min-height: 100vh;
  background-color: #f1f1f1;
    font-family: 'Lato', sans-serif;
  font-family: 'Poppins', sans-serif;
}

.contents {
  padding-bottom: 10rem;
  background-color: #f1f1f1;
}


div #nav {
  display: flex;
  justify-content: space-evenly;
  padding: 1rem 0rem 1rem 0rem;
  background-color: #659dbd;
  font-size: 1rem;
  font-weight: bold;
  font-family: 'Lato', sans-serif;
  font-family: 'Poppins', sans-serif;;
}

#nav:link {
  text-decoration: none;
}

a:link {
  text-decoration: none;
  color: #f1f1f1;
}

a:visited {
  text-decoration: none;
  color: #f1f1f1;
}


footer {
  background-color: #659dbd;
  margin-top: 3rem;
  color: #f1f1f1;
  border-width: 2px;
  border-color: black;
  width: 100%;
  position: absolute;
  bottom: 0;
}

#footer-text {
  padding: 40px;
}

</style>
