<template>
  <div class="pdf">
    <button class="btn" @click="downloadPDF">Dowload as PDF</button>
    <div ref="content">
      <!-- <chartColumn /> -->
      <chartBar />
    </div>
  </div>
</template>

<script>
import jsPDF from "jspdf";
import html2canvas from "html2canvas";

//import chartColumn from "./chartColumn";
import chartBar from "./chartBar";

export default {
  name: "pdf",
  components: {
    chartBar,
  },
  data() {
    return {};
  },
  methods: {
    async downloadPDF() {
      const pdf = new jsPDF("p", "pt", "a4");
      const parentRoot = document.getElementById("chart-container");
      const parent = parentRoot.childNodes[0];
      const element = parent.childNodes[0];
      let svg = element.childNodes[0];

      html2canvas(svg).then(function (canvas) {
        const imgData = canvas.toDataURL("image/png");
        console.log(imgData);
        pdf.addImage(imgData, "PNG", 40, 40, 400, 250);
        pdf.save("relatorio.pdf");
      });
    },
  },
  props: {},
};
</script>