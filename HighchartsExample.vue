<template>
  <vue-highcharts
    type="chart"
    :options="chartOptions"
    :redrawOnUpdate="true"
    :oneToOneUpdate="false"
    :animateOnUpdate="true"
    @rendered="onRender"/>
</template>
<script>
  //import VueHighcharts from 'https://cdn.skypack.dev/vue3-highcharts';
  import VueHighcharts from 'https://unpkg.com/browse/vue3-highcharts@0.1.3/dist/vue3-highcharts.common.mjs'
  //import VueHighcharts from 'vue3-highcharts';

  export default {
    name: 'HighchartsExample',

    components: {
      VueHighcharts,
    },

    setup() {
      const seriesData = ref([25, 39, 30, 15]);
      const categories = ref(['Jun', 'Jul', 'Aug', 'Sept']);

      const chartOptions = computed(() => ({
        chart: {
          type: 'line',
        },
        title: {
          text: 'Number of project stars',
        },
        xAxis: {
          categories: categories.value,
        },
        yAxis: {
          title: {
            text: 'Number of stars',
          },
        },
        series: [{
          name: 'New project stars',
          data: seriesData.value,
        }],
      }));

      const onRender = () => {
        console.log('Chart rendered');
      };

      return {
        chartOptions,
        onRender,
      };
    },
  };
</script>
