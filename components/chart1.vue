<template>
  <chartist
    type="Pie"
    :data="chartData"
    :options="chartOptions">
  </chartist>
</template>

<script>
export default {
  name: 'chart1',
  props: {
    chartData: {
      type: Object,
      default () {
        return {
          labels: ['car', 'public transport'],
          series: [0, 60, 0, 0]
        }
      }
    }
  },
  data () {
    return {
      chartOptions: {
        donut: true,
        donutWidth: 80,
        showLabel: true,
        width: '100%'
      }
    }
  }
}
</script>

<style>
.ct-series-a .ct-slice-donut {
  stroke: #F19C79;
}

.ct-series-b .ct-slice-donut {
  stroke: #CBDFBD;
}

.ct-series-c .ct-slice-donut {
  stroke: #F6F4D2;
}

.ct-series-d .ct-slice-donut {
  stroke: #D4E09B;
}

.ct-chart-donut>g>.ct-label {
  fill: black;
  color: whitesmoke;
  font-size: 18px;
}
</style>
