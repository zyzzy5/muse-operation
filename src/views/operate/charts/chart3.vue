<template>
    <div ref="chartthree" class="container"></div>
</template>

<script>
import echarts from 'echarts'

export default {
  name: 'chart-three',
  mounted () {
    this.drawline()
  },
  methods: {
    drawline () {
      const chartObj = echarts.init(this.$refs.chartthree)
      chartObj.setOption({
        color: ['#26051836', '#EEA53A'],
        tooltip: {
          trigger: 'item'
        },
        legend: {
          orient: 'vertical',
          left: 10,
          data: ['', '']
        },
        series: [
          {
            name: '',
            type: 'pie',
            radius: ['90%', '80%'],
            avoidLabelOverlap: false,
            hoverAnimation: false,
            label: {
              show: false,
              position: 'center'
            },
            emphasis: {
              label: {
                show: true,
                fontSize: '30',
                fontWeight: 'bold'
              }
            },
            labelLine: {
              show: false
            },
            data: [
              { value: 40, name: '' },
              { value: 60, name: '' }
            ]
          }
        ]
      })
    }
  }
}
</script>

<style lang="less" scoped>
.container {
    height: 80px;
    width:80px;
}
</style>