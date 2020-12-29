<template>
  <div id="appContainer">
    <Header />

    <div id="content">
      <router-view></router-view>
    </div>
  </div>
</template>

//? script part ////////////////////////////////////////////////////////
<script>
import Header from "./components/layout/Header";

export default {
  name: "App",
  components: {
    Header,
  },
};
</script>

///? /////////////////////////////////////////////////////////////////////

<style>
#appContainer {
}
</style>
