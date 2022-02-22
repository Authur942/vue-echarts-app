<template>
  <div>
    <div id="myChart" :style="{ width: '300px', height: '300px' }"></div>
    <div id="myChart2" :style="{ width: '550px', height: '550px',padding: '50px' }"></div>
  </div>
</template>

<script>
export default {
  name: 'Table',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  mounted () {
    this.drawLine()
  },
  methods: {
    drawLine () {
      // 基于准备好的dom，初始化echarts实例
      let myChart = this.$echarts.init(document.getElementById('myChart'))
      let myChart2 = this.$echarts.init(document.getElementById('myChart2'))
      // 绘制图表
      myChart.setOption({
        title: { text: '柱状图' },
        tooltip: {},
        xAxis: {
          data: ["衬衫", "羊毛衫", "雪纺衫", "裤子", "高跟鞋", "袜子"]
        },
        yAxis: {},
        series: [{
          name: '销量',
          type: 'bar',
          data: [5, 20, 36, 10, 10, 20]
        }]
      });
      myChart2.setOption({
        title: { text: '玫瑰图' },
        legend: {
          orient: "horizontal",
          padding: [40,0,0,0],
          left: "left",
          data: ["Apple", "Grapes", "Pineapples", "Oranges", "Bananas"]
        },
        series: [{
          name: '销量',
          type: 'pie',
          data: [{
            value: 335,
            name: "Apple"
          }, {
            value: 310,
            name: "Grapes"
          }, {
            value: 234,
            name: "Pineapples"
          }, {
            value: 135,
            name: "Oranges"
          }, {
            value: 1548,
            name: "Bananas"
          }]
        }]
      });
    }
  }
}
</script>

<style lang='scss' scoped>
</style>
