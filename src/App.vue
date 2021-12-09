<template>
  <header class="header">
    <div class="header__text">Test SPA on Vue.js</div>
  </header>

  <router-view/>

  <footer class="footer">
    <h1>The end. Thank you!</h1>
  </footer>
</template>

<style lang="scss">
body {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;

  margin: 0;
  background: #b9e796;
  background: linear-gradient(137deg, #b9e796 0%, #ffa541 100%);
  font: 400 14px/1.4 #2c3e50;
	scroll-behavior: smooth;
	min-width: 320px;
	overflow-y: scroll;
}

.header {
  height: 60px;
  background: #ffffff;
  font-size: 20px;

  &__text {
    margin-left: 40px;
    padding-top: 15px;

    &::before {
      content: '';
      width: 27px;
      height: 27px;
      background: url("./assets/logo.png") center no-repeat;
      background-size: 27px;
      display: inline-block;
      margin-right: 5px;
      margin-bottom: -5px;
    }
  }
}

.footer {
  height: 160px;
  background: #2c3e50;
  color: #ffffff;

  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
