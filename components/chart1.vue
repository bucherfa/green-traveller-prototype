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
  stroke: #023E8A;
}

.ct-series-b .ct-slice-donut {
  stroke: #0096C7;
}

.ct-series-c .ct-slice-donut {
  stroke: #48CAE4;
}

.ct-series-d .ct-slice-donut {
  stroke: #ADE8F4;
}

.ct-chart-donut>g>.ct-label {
  fill: darkblue;
  color: whitesmoke;
  font-size: 18px;
}
</style>
