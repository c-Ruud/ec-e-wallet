<template>
  <header class="top">
    <h1>Welcome to e-Wallet</h1>
    <div class="links">
      <router-link to="/">Home</router-link> |
      <router-link to="/addcard">Add Card</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <hr />
    <!--<p class="card-type">Your card</p>-->
  </header>
</template>

<script>
export default {};
</script>

<style scoped>
.links {
  text-align: center;
}
hr {
  margin-bottom: 20px;
  margin-top: 10px;
}
.top {
  display: -ms-flexbox;
  display: -webkit-box;
  display: flex;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
  -ms-flex-direction: column;
  flex-direction: column;
  text-transform: uppercase;
}
.top p {
  -webkit-box-flex: 1;
  -ms-flex: 1;
  flex: 1;
  font-size: 0.8rem;
  font-weight: 600;
  color: rgba(0, 0, 0, 0.4);
  padding: 0.25rem;
}
p {
  display: block;
  margin-block-start: 1em;
  margin-block-end: 1em;
  margin-inline-start: 0px;
  margin-inline-end: 0px;
}
.top h1,
.top p {
  text-align: center;
  margin: 0;
}
</style>
