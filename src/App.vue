<template>
  <div id="app">
    <Header />

    <main>
      <DiskList />
    </main>

  </div>
</template>

<script>
import Header from "./components/Header";
import DiskList from "./components/DiskList";

export default {
  name: "App",
  components: {
    Header,
    DiskList
  },
};
</script>

<style lang="scss">
@import './style/general';
@import './style/utilities';

body {
  background-color: #1e2d3b;
}
</style>
