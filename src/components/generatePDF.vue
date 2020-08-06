<template>
  <div class="pdf">
    <button class="btn" @click="downloadPDF">Dowload as PDF</button>
    <div ref="content">
      <chartColumn />
      <chartBar />
    </div>
  </div>
</template>

<script>
//import jsPDF from "jspdf";

import chartColumn from "./chartColumn";
import chartBar from "./chartBar";

export default {
  name: "pdf",
  components: {
    chartBar,
    chartColumn,
  },
  data() {
    return {};
  },
  methods: {
    //GET CHART HTML CODE
    downloadPDF() {
      const html = this.$refs.content.innerHTML;
      console.log(html);
    },
  },
  props: {},
};
</script>