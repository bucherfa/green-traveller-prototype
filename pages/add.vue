<template>
  <div class="container">
    <div>
      <span>From</span>
      <a-input placeholder="Berlin" value="Ernst-Reuter-Platz" />
    </div>
    <div>
      <span>To</span>
      <a-input placeholder="Somewhere" value="Alt-Friedrichsfelde 60" />
    </div>
    <div class="makespace">
      <span>CO2</span>
      <chartist type="Bar" :data="co2" :options="chartOptions"></chartist>
    </div>
    <div class="makespace">
      <span>Duration</span>
      <chartist type="Bar" :data="time" :options="chartOptions"></chartist>
    </div>
    <div class="select">
      <a-radio-group>
        <a-radio-button value="a">
          Car
        </a-radio-button>
        <a-radio-button value="c">
          Public Transport
        </a-radio-button>
        <a-radio-button value="b">
          Bike
        </a-radio-button>
        <a-radio-button value="d">
          Walking
        </a-radio-button>
      </a-radio-group>
    </div>
    <nuxt-link to="/">
      <a-button class="moveup" type="primary" block size="large">
        Add
      </a-button>
    </nuxt-link>
  </div>
</template>

<script>
export default {
  name: 'add',
  data () {
    return {
      co2: {
        labels: ['car', 'public transport', 'bike', 'walking'],
        series: [['30', '20', '0', '0']]
      },
      time: {
        labels: ['car', 'public transport', 'bike', 'walking'],
        series: [['40', '60', '51', '180']]
      },
      chartOptions: {
        showLabel: true,
        height: '11rem'
      }
    }
  }
}
</script>

<style>
.ct-bar {
  stroke: #7BAE7F !important;
}
.makespace {
  height: 12rem;
}
.container {
  padding: 0.5rem;
}

.select {
  text-align: center;
  margin: 1rem 0;
}
</style>
