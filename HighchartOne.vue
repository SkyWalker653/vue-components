<template>
    <highcharts :options="chartOptions"></highcharts>
</template>

<script>
// import HighchartsVue from 'highcharts-vue'
import { Chart } from 'https://unpkg.com/highcharts-vue@1.3.5/dist/highcharts-vue.min.js'

export default {
  data () {
    return {
      chartOptions: {
        series: [{
          data: [1, 2, 3] // sample data
        }]
      }
    }
  },
  components: {
    highcharts: Chart
  }
}
</script>
