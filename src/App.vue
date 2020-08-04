//STEP 4: Render the chart
<template>
  <div id="app">
    <div id="chart-container">
      <fusioncharts
        :type="type"
        :width="width"
        :height="height"
        :dataformat="dataFormat"
        :dataSource="dataSource"
      ></fusioncharts>
      <fusioncharts
        :type="type"
        :width="width"
        :height="height"
        :dataformat="dataFormat"
        :dataSource="dataSource"
      ></fusioncharts>
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
const chartColumnData = require("./resources/chartColumnData.json");
// STEP 3: Configure your chart
const dataSource = {
  chart: {
    caption: "Countries With Most Oil Reserves [2017-18]",
    subcaption: "In MMbbl = One Million barrels",
    xaxisname: "Country",
    yaxisname: "Reserves (MMbbl)",
    numbersuffix: "K",
    theme: "fusion",
    crossLineAnimation: "0",
    exportEnabled: 1,
  },
  data: chartColumnData,
};

export default {
  name: "app",
  data() {
    return {
      type: "column2d",
      renderAt: "chart-container",
      width: "550",
      height: "350",
      dataFormat: "json",
      dataSource: dataSource,
    };
  },
};
</script>