<template>
    <div ref="charttwo" class="container"></div>
</template>

<script>
import echarts from 'echarts'

export default {
  name: 'chart-two',
  mounted () {
    this.drawline()
  },
  methods: {
    drawline () {
      const chartObj = echarts.init(this.$refs.charttwo)
      chartObj.setOption({
        color: ['#26051836', '#E55A23'],
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
              { value: 30, name: '' },
              { value: 70, name: '' }
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