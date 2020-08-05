<template>
  <div id="app">
    <generatePDF />
  </div>
</template>


<script>
// import chartColumn from "./components/chartColumn";
// import chartBar from "./components/chartBar";
import generatePDF from "./components/generatePDF";
export default {
  name: "App",
  components: {
    generatePDF,
  },
};
</script>

<style lang="scss">
</style>