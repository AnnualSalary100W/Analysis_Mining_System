
<template>
    <div id="myChart" :style="{width: '1000px', height: '500px'}"></div>
</template>

<script>


    export default {
        name: '',
        data () {
            return {
                msg: ''
            }
        },
        mounted(){
            this.drawLine();
        },
        methods: {
            drawLine(){
                // 基于准备好的dom，初始化echarts实例
                let myChart = this.$echarts.init(document.getElementById('myChart'))
                // 绘制图表
                myChart.setOption({
                    title: { text: '出行分析结果可视化图' },
                    tooltip: {},
                    xAxis: {
                        data: ["步行","自行车","地铁","电动车","私家车","公交车"]
                    },
                    yAxis: {},
                    series: [{
                        name: '销量',
                        type: 'bar',
                        data: [508, 2012, 3653, 1001, 3205, 2855]
                    }]
                });
            }
        }
    }
</script>

<style scoped>

</style>