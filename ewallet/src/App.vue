<template>
  <div id="app">
    <div id="nav">
      <!-- <button v-on:click="router-link to="/addcard" type="button">Add new card</button>-->
    </div>
    <router-view />
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss">
//@import url("https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css");
@import url("https://fonts.googleapis.com/css2?family=Dosis:wght@300&display=swap");
#app {
  font-family: Dosis, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  max-width: 24rem;
  height: 100vh;
  padding: 1rem;
  margin: 0 auto;
  box-sizing: border-box;
  -webkit-box-sizing: border-box;
}

button {
  &:hover {
    color: black;
    cursor: pointer;
  }
  #nav {
    padding: 30px;

    a {
      font-weight: bold;
      color: #2c3e50;

      &.router-link-exact-active {
        color: #42b983;
      }
    }
  }
  a.cta {
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -webkit-box-pack: center;
    -ms-flex-pack: center;
    justify-content: center;
    -webkit-box-align: center;
    -ms-flex-align: center;
    align-items: center;
    height: 4rem;
    font-size: 1.2rem;
    text-transform: uppercase;
    font-weight: 700;
    text-decoration: none;
    color: #000;
    border: 0.125rem solid #000;
    -webkit-box-sizing: border-box;
    box-sizing: border-box;
    border-radius: 0.5rem;
    margin: 2rem 0;
  }
  a:-webkit-any-link {
    color: -webkit-link;
    cursor: pointer;
    text-decoration: underline;
  }
}
</style>
