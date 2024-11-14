<template>
  <div class="chart-container">
    <Chart
      height="90%"
      width="100%"
      :chart-title="'年度成绩概览'"
      :legend-data="['课程成绩', '科研成绩', '总体平均成绩']"
      :x-axis-data="['1月', '2月', '3月', '4月', '5月', '6月', '7月', '8月', '9月', '10月', '11月', '12月']"
      :series-data="seriesData"
    />
    <el-button icon="el-icon-question" type="primary">
      Generate Personalized Advising
    </el-button>
  </div>
</template>

<script>
import Chart from '@/components/Charts/MixChart'

export default {
  name: 'MixChart',
  components: { Chart },
  data() {
    return {
      seriesData: [
        {
          name: '课程成绩',
          type: 'bar',
          stack: 'total',
          barMaxWidth: 35,
          barGap: '10%',
          itemStyle: {
            normal: {
              color: 'rgba(255,144,128,1)',
              label: {
                show: true,
                textStyle: {
                  color: '#fff'
                },
                position: 'insideTop',
                formatter(p) {
                  return p.value > 0 ? p.value : ''
                }
              }
            }
          },
          data: [70, 191, 245, 261, 171, 143, 154, 328, 520, 337, 248, 407]
        },
        {
          name: '科研成绩',
          type: 'bar',
          stack: 'total',
          itemStyle: {
            normal: {
              color: 'rgba(0,191,183,1)',
              barBorderRadius: 0,
              label: {
                show: true,
                position: 'top',
                formatter(p) {
                  return p.value > 0 ? p.value : ''
                }
              }
            }
          },
          data: [32, 177, 50, 120, 80, 48, 20, 139, 100, 95, 38, 22]
        },
        {
          name: '总体平均成绩',
          type: 'line',
          stack: 'total',
          symbolSize: 10,
          symbol: 'circle',
          itemStyle: {
            normal: {
              color: 'rgba(252,230,48,1)',
              barBorderRadius: 0,
              label: {
                show: true,
                position: 'top',
                formatter(p) {
                  return p.value > 0 ? p.value : ''
                }
              }
            }
          },
          data: [102, 368, 295, 381, 251, 191, 174, 467, 620, 432, 286, 429]
        }
      ]
    }
  }
}
</script>

  <style scoped>
  .chart-container{
    position: relative;
    width: 100%;
    height: calc(100vh - 84px);
  }
  </style>
