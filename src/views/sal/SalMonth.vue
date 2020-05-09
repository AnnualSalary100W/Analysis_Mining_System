<template>
  <div>
    <div class="pie">
        <div id="pie1">
            <!-- 为 ECharts 准备一个具备大小（宽高）的 DOM -->
            <div id="main1" style="float:left;width:100%;height: 400px"></div>
        </div>
        <div id="pie2">
            <div id="main2" style="float:left;width:100%;height: 300px"></div>
        </div>
    </div>
  </div>
</template>

<script>// 引入基本模板
let echarts = require('echarts/lib/echarts')
// 引入饼状图组件
require('echarts/lib/chart/pie')
// 引入提示框和title组件
require('echarts/lib/component/tooltip')
require('echarts/lib/component/title')


export default {
  created(){
  },
  mounted(){
    this.initData();
  },
  methods:{
    //初始化数据
    initData() {
      // 基于准备好的dom，初始化echarts实例
      var myChart = echarts.init(document.getElementById('main1'));
      // 绘制图表
      myChart.setOption({
          title : {
              text: '出行方式分析结果推荐表',//主标题
              subtext: '推荐程度百分比',//副标题
              x:'center',//x轴方向对齐方式
          },
          tooltip : {
              trigger: 'item',
              formatter: "{a} <br/>{b} : {c} ({d}%)"
          },
          legend: {
              orient: 'vertical',
              bottom: 'bottom',
              data: ['公交','自行车','电动车','私家车','地铁']
          },
          series : [
              {
                  name: '推荐程度',
                  type: 'pie',
                  radius : '55%',
                  center: ['50%', '60%'],
                  data:[
                      {value:335, name:'公交'},
                      {value:310, name:'自行车'},
                      {value:234, name:'电动车'},
                      {value:135, name:'私家车'},
                      {value:1548, name:'地铁'}
                  ],
                  itemStyle: {
                      emphasis: {
                          shadowBlur: 10,
                          shadowOffsetX: 0,
                          shadowColor: 'rgba(0, 0, 0, 0.5)'
                      }
                  }
              }
          ]
      });
    },
  }
}
</script>