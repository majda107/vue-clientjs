<template>
  <div id="app">
    <div class="data-wrapper">
      <ClientData />
    </div>
  </div>
</template>

<script>
import ClientData from "./components/ClientData.vue";

export default {
  name: "App",
  components: {
    ClientData
  }
};
</script>

<style>
#app {
  font-family: 'Roboto';
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;

  background: rgb(119, 18, 109);
  background: -moz-linear-gradient(
    123deg,
    rgba(119, 18, 109, 1) 0%,
    rgba(16, 84, 134, 1) 100%
  );
  background: -webkit-linear-gradient(
    123deg,
    rgba(119, 18, 109, 1) 0%,
    rgba(16, 84, 134, 1) 100%
  );
  background: linear-gradient(
    123deg,
    rgba(119, 18, 109, 1) 0%,
    rgba(16, 84, 134, 1) 100%
  );
  filter: progid:DXImageTransform.Microsoft.gradient(startColorstr="#77126d",endColorstr="#105486",GradientType=1);

  min-height: 100vh;
  display: flex;
  align-items: center;
}

* {
  padding: 0;
  margin: 0;
  color: #dbdbdb;
}

.data-wrapper {
  width: 100%;
  display: flex;
  justify-content: center;
  padding-top: 80px;
  padding-bottom: 80px;
  padding-left: 36px;
  padding-right: 36px;
}
</style>

<style lang="scss">
html,
body {
  margin: 0;
  padding: 0;
}

body {
  background-color: #31102f; //#280B29
  background: radial-gradient(
    ellipse at center,
    rgba(49, 16, 47, 1) 0%,
    rgba(40, 11, 41, 1) 100%
  );
}

#stars {
  display: block;
  position: relative;
  width: 100%;
  height: 16rem;
  height: 100vh;
  z-index: 1;
}

</style>