<template>
  <div>
  <div id="main" class="order"></div>
    <div id="main1" class="gauge1"></div>
    <div id="main2" class="gauge2"></div>
    <div id="main3" class="gauge3"></div>
    <div id="main4" class="gauge4"></div>
  </div>
</template>

<script>
import echarts from 'echarts'
export default {
  name: '',
  data () {
    return {
      charts: '',
      charts1: '',
      charts2: '',
      charts3: '',
      charts4: '',
      opinion: ['物料风险', '人员风险', '设备风险', '质量风险'],
      color: ['#3efbc9', '#0059ff', '#41d0f2', '#FF0000'],
      goodsdata: [
        [145.6, 60], [170.1, 61.2], [165.0, 55.2], [178.0, 74.9], [155.5, 58.8],
        [165.6, 81.0], [160.7, 69.1], [163.2, 55.9], [152.4, 46.5], [157.5, 54.3]
      ],
      persondata: [[167.6, 58.3], [165.1, 56.2], [160.0, 50.2], [170.0, 72.9], [157.5, 59.8],
        [167.6, 61.0], [160.7, 69.1], [163.2, 55.9], [152.4, 46.5], [157.5, 54.3]],
      equipmentdata: [[161.0, 53.6], [151.1, 73.2], [168.2, 53.4], [168.9, 69.0], [173.2, 58.4],
        [171.8, 56.2], [178.0, 70.6], [164.3, 59.8], [163.0, 72.0], [168.5, 65.2],
        [166.8, 56.6], [172.7, 105.2], [163.5, 51.8], [169.4, 63.4], [167.8, 59.0]],
      qualitydata: [ [157.5, 63.6], [162.6, 54.5], [152.4, 47.3], [170.2, 67.7], [165.1, 80.9],
        [172.7, 70.5], [165.1, 60.9], [170.2, 63.6], [170.2, 54.5], [170.2, 59.1],
        [161.3, 70.5], [167.6, 52.7], [167.6, 62.7], [165.1, 86.3], [162.6, 66.4]
      ]
    }
  },
  components: {
  },
  methods: {
    drawGauge1 (id) {
      // var sum = 0
      // for (var point in this.goodsdata) {
      //   alert('22' + point.x)
      //   sum = sum + point[1]
      // }
      this.charts1 = echarts.init(document.getElementById(id))
      this.charts1.setOption({
        max: 1000,
        tooltip: {
          formatter: '{a} <br/>{b} :{c}%'
        },
        series: [{
          name: '物料风险',
          type: 'gauge',
          detail: {
            formatter: '{value}',
            show: true,
            offsetCenter: [0, '5%']
          },
          startAngle: 180,
          endAngle: 0,
          axisLine: {
            lineStyle: {
              width: 15
            }
          },
          axisLabel: {
            show: false
          },
          pointer: {
            length: '0',
            width: 0
          },
          spliteLine: {
            lineStyle: {
              width: 2
            }
          },
          data: [{value: 50, name: '物料风险'}]
        }]
      })
    },
    drawGauge2 (id) {
      this.charts2 = echarts.init(document.getElementById(id))
      this.charts2.setOption({
        max: 1000,
        tooltip: {
          formatter: '{a} <br/>{b} :{c}%'
        },
        series: [{
          name: '人员风险',
          type: 'gauge',
          detail: {
            formatter: '{value}',
            show: true,
            offsetCenter: [0, '5%']
          },
          startAngle: 180,
          endAngle: 0,
          axisLine: {
            lineStyle: {
              width: 15
            }
          },
          axisLabel: {
            show: false
          },
          pointer: {
            length: '0',
            width: 0
          },
          spliteLine: {
            lineStyle: {
              width: 2
            }
          },
          data: [{value: 50, name: '人员风险'}]
        }]
      })
    },
    drawGauge3 (id) {
      this.charts3 = echarts.init(document.getElementById(id))
      this.charts3.setOption({
        max: 1000,
        tooltip: {
          formatter: '{a} <br/>{b} :{c}%'
        },
        series: [{
          name: '设备风险',
          type: 'gauge',
          detail: {
            formatter: '{value}',
            show: true,
            offsetCenter: [0, '5%']
          },
          startAngle: 180,
          endAngle: 0,
          axisLine: {
            lineStyle: {
              width: 15
            }
          },
          axisLabel: {
            show: false
          },
          pointer: {
            length: '0',
            width: 0
          },
          spliteLine: {
            lineStyle: {
              width: 2
            }
          },
          data: [{value: 50, name: '设备风险'}]
        }]
      })
    },
    drawGauge4 (id) {
      this.charts3 = echarts.init(document.getElementById(id))
      this.charts3.setOption({
        max: 1000,
        tooltip: {
          formatter: '{a} <br/>{b} :{c}%'
        },
        series: [{
          name: '质量风险',
          type: 'gauge',
          detail: {
            formatter: '{value}',
            show: true,
            offsetCenter: [0, '5%']
          },
          startAngle: 180,
          endAngle: 0,
          axisLine: {
            lineStyle: {
              width: 15
            }
          },
          axisLabel: {
            show: false
          },
          pointer: {
            length: '0',
            width: 0
          },
          spliteLine: {
            lineStyle: {
              width: 2
            }
          },
          data: [{value: 50, name: '质量风险'}]
        }]
      })
    },
    drawPie (id) {
      this.charts = echarts.init(document.getElementById(id))
      this.charts.setOption({
        title: {
          text: '订 单 执 行',
          fontSize: 18,
          fontWeight: 'bolder'
        },
        tooltip: {
          trigger: 'item',
          formatter: '{a}<br/>{b}:{c})'
        },
        color: this.color,
        legend: {
          orient: 'horizontal',
          x: 'center',
          y: 'bottom',
          data: this.opinion
        },
        xAxis: [{
          type: 'value',
          scale: true,
          axisTick: {
            show: false
          }
        }],
        yAxis: [{
          type: 'value',
          show: 'true',
          axisTick: {
            show: false
          },
          axisLabel: {
            textStyle: {
              color: 'whilte'
            }
          }
        }],
        series: [
          {
            name: '物料风险',
            type: 'scatter',
            data: this.goodsdata
          }, {
            name: '人员风险',
            type: 'scatter',
            data: this.persondata
          }, {
            name: '设备风险',
            type: 'scatter',
            data: this.equipmentdata
          }, {
            name: '质量风险',
            type: 'scatter',
            data: this.qualitydata
          }
        ]
      })
    }
  },
  mounted () {
    this.$nextTick(function () {
      this.drawPie('main')
      this.drawGauge1('main1')
      this.drawGauge2('main2')
      this.drawGauge3('main3')
      this.drawGauge4('main4')
    })
  }
}
</script>

<style scoped>
  .order {
    width:1200px; height:600px;
    color: white;
    margin: 0;
    padding: 0;
    list-style: none;
  }
  .gauge1 {
    width:320px; height:300px;
    position: absolute;
    left: 1100px;
    top: 10px;
    color: white;
    margin: 0;
    padding: 0;
    list-style: none;
  }
  .gauge2 {
    width:320px; height:300px;
    position: absolute;
    left: 1100px;
    top: 150px;
    color: white;
    margin: 0;
    padding: 0;
    list-style: none;
  }
  .gauge3 {
    width:320px; height:300px;
    position: absolute;
    left: 1100px;
    top: 300px;
    color: white;
    margin: 0;
    padding: 0;
    list-style: none;
  }
  .gauge4 {
    width:320px; height:300px;
    position: absolute;
    left: 1100px;
    top: 450px;
    color: white;
    margin: 0;
    padding: 0;
    list-style: none;
  }
</style>
