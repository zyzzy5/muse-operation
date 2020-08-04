<template>
    <div ref="liquidFill" class="container"></div>
</template>

<script>
import echarts from 'echarts'
import 'echarts-liquidfill'

export default {
  name: 'liquid-fill',
  mounted () {
    this.drawline()
  },
  methods: {
    drawline () {
      const chartObj = echarts.init(this.$refs.liquidFill)
      chartObj.setOption({
        title: {
          text: '终端异常',
          left: 'center',
          top: 10,
          textStyle: {
            color: '#333',
            fontWeight: 'normal',
            fontSize: 14
          }
        },
        series: [{
          name: '水球图',
          type: 'liquidFill',
          radius: '80%',
          center: ['50%', '55%'],
          waveAnimation: 10, // 动画时长
          amplitude: 20, // 振幅
          data: [0.6],
          color: 'rgba(68, 197, 253,1)',
          label: {
            normal: {
              color: '#44C5FD',
              textStyle: {
                fontSize: 16,
                fontWeight: 'normal'
              }
            }
          },
          outline: {
            show: true,
            borderDistance: 5,
            itemStyle: {
              borderColor: 'rgba(68, 197, 253,1)',
              borderWidth: 2
            }
          },
          backgroundStyle: {
            color: 'rgba(68, 197, 253,.3)'
          }
        }]
      })
    }
  }
}
</script>

<style lang="less" scoped>
.container {
    height: 167px;
    width:168px;
}
</style>
