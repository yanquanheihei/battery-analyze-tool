<template>
  <div>
    <div id="demo"></div>
  </div>
</template>

<script>
export default {
  name: 'BatteryCurve',
  data () {
    return {
      option: {
        title: {
          text: '电量曲线',
          left: 'center'
        },
        tooltip: {
          trigger: 'axis',
          axisPointer: {
            type: 'cross',
            label: {
              backgroundColor: '#6a7985'
            }
          }
        },
        legend: {
          bottom: '5%',
          data: ['时间']
        },
        xAxis: {
          axisTick: {
            show: false
          },
          axisLine: {
            show: true
          },
          type: 'category',
          data: ['16:28:41', '16:28:42', '16:28:43', '16:28:44', '16:28:45', '16:28:46', '16:28:47'],
          boundaryGap: false
        },
        yAxis: {
          axisTick: {
            show: true
          },
          axisLine: {
            show: true
          },
          type: 'value',
          axisLabel: {
            formatter: '{value}(%)'
          }
        },
        grid: {
          left: '5%',
          right: '5%',
          bottom: '20%',
          containLabel: true
        },
        series: [{
          name: '电量',
          symbol: 'circle',
          data: [33, 44, 66, 89, 77, 78, 63],
          type: 'line',
          smooth: true,
          areaStyle: {
            // color: 'lightblue'
          }
        }]
      }
    }
  },
  mounted () {
    this.drawLine()
  },
  methods: {
    drawLine () {
      let chartDom = document.getElementById('demo')
      let myChart = this.$echarts.init(chartDom)
      myChart.setOption(this.option)
      window.addEventListener('resize', () => {
        myChart.resize()
      })
    }
  }
}
</script>

<style scoped>
#demo {
  margin: 0 auto;
  width: 100%;
  height: 500px;
  background-color: #E9EEF3;
}
</style>
