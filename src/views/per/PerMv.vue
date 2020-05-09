<
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
                    title: { text: '驻留分析结果可视化图' },
                    tooltip: {},
                    xAxis: {
                        data: ["太原街","中街","五爱","三台子地铁口","沈阳站","沈阳北站"]
                    },
                    yAxis: {},
                    series: [{
                        name: '销量',
                        type: 'bar',
                        data: [2509, 5022, 4653, 3001, 6205, 5855]
                    }]
                });
            }
        }
    }
</script>

<style scoped>

</style>