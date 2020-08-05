//STEP 4: Render the chart
<template>
  <div id="bar">
    <div id="chart-container">
      <fusioncharts
        :type="type"
        :width="width"
        :height="height"
        :dataformat="dataFormat"
        :dataSource="dataSource"
      ></fusioncharts>
    </div>
  </div>
</template>
// STEP 1: to include the dependencies
<script>
import Vue from "vue";
import VueFusionCharts from "vue-fusioncharts";
import FusionCharts from "fusioncharts";
import Column2D from "fusioncharts/fusioncharts.charts";
import FusionTheme from "fusioncharts/themes/fusioncharts.theme.fusion";

Vue.use(VueFusionCharts, FusionCharts, Column2D, FusionTheme);

// STEP 2: Prepare the data
const chartBarData = require("./../resources/chartBarData.json");
// STEP 3: Configure your chart
const dataSource = {
  chart: {
    caption: "Top 5 Stores by Sales",
    subCaption: "Last month",
    yAxisName: "Sales (In USD)",
    numberPrefix: "$",
    theme: "fusion",
    crossLineAnimation: 0,
    exportEnabled: 1,
  },
  data: chartBarData,
};

export default {
  name: "chartBar",
  data() {
    return {
      type: "bar2d",
      renderAt: "chart-container",
      width: "550",
      height: "350",
      dataFormat: "json",
      dataSource: dataSource,
    };
  },
};
</script>