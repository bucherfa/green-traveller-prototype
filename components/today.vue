<template>
  <div class="container">
    <h2>Today</h2>
    <div class="select">
      <a-radio-group v-model="value">
        <a-radio-button value="co2">
          CO2
        </a-radio-button>
        <a-radio-button value="distance">
          Distance
        </a-radio-button>
        <a-radio-button value="time">
          Time
        </a-radio-button>
      </a-radio-group>
    </div>
    <div class="chart">
      <chart1 :chart-data="chart[value]"></chart1>
    </div>
    <div>
      <h3>Trips</h3>
      <a-table :columns="columns" :data-source="data" :pagination="false">
      </a-table>
    </div>
  </div>
</template>

<script>
import Chart1 from '~/components/chart1'

const columns = [
  {
    title: 'From',
    dataIndex: 'from',
    key: 'from'
  },
  {
    title: 'To',
    dataIndex: 'to',
    key: 'to'
  },
  {
    title: 'Type',
    dataIndex: 'type',
    key: 'type'
  },
  {
    title: 'Impact',
    dataIndex: 'impact',
    key: 'impact'
  }
]

const data = [
  {
    key: '1',
    from: 'Frie-drichs-felde-Ost 60',
    to: 'Ernst-Reuter-Platz',
    type: 'public transport',
    impact: 'low'
  },
  {
    key: '2',
    from: 'Ernst-Reuter-Platz',
    to: 'Frie-drichs-felde-Ost 60',
    type: 'public transport',
    impact: 'low'
  }
]

const chart = {
  co2: {
    labels: ['car', 'public transport'],
    series: [90, 30]
  },
  time: {
    labels: ['car', 'public transport', 'bike', 'walking'],
    series: [15, 60, 20, 20]
  },
  distance: {
    labels: ['car', 'public transport', 'bike', 'walking'],
    series: [50, 40, 5, 2]
  }
}

export default {
  components: { Chart1 },
  data () {
    return {
      columns,
      data,
      value: 'co2',
      chart
    }
  }
}
</script>

<style scoped>
.select {
  text-align: right;
}

.chart {
  margin-top: 1rem;
  text-align: center;
}
</style>
