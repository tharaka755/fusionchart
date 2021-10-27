<template>
  <div class="hello">
    <fusioncharts
      :type="type"
      :width="width"
      :height="height"
      dataFormat="json"
      :dataSource="dataSource"
    ></fusioncharts>
  </div>
</template>

<script>
import FusionCharts from 'fusioncharts';
import { FCComponent } from "vue-fusioncharts"
import Charts from 'fusioncharts/fusioncharts.charts';

Charts(FusionCharts)

const dataSource = {
  chart: {
    caption: "Android Distribution for our app",
    subcaption: "For all users in 2017",
    showpercentvalues: "1",
    defaultcenterlabel: "Android Distribution",
    aligncaptionwithcanvas: "0",
    captionpadding: "0",
    decimals: "1",
    plottooltext:
      "<b>$percentValue</b> of our Android users are on <b>$label</b>",
    centerlabel: "# Users: $value",
    theme: "fusion"
  },
  data: [
    {
      label: "Ice Cream Sandwich",
      value: "1000"
    },
    {
      label: "Jelly Bean",
      value: "5300"
    },
    {
      label: "Kitkat",
      value: "10500"
    },
    {
      label: "Lollipop",
      value: "18900"
    },
    {
      label: "Marshmallow",
      value: "17904"
    }
  ]
};

export default {
  name: 'Chart',

  composnents: {
    fusioncharts: FCComponent,
  },

  props: [
    'type',
    'width',
    'height',
  ],

  data() {
    return {
      dataSource,
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
