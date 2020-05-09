<template lang="html">
    <div id="load">
        <!--存放百度地图容器-->
        <div id="container"></div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                // 热力图的点数据，lng：点的经度 点的lat纬度 count：点的热力程度
                points: [
                    {"lng":123.418261,"lat":41.921984,"count":50},
                    {"lng":123.423332,"lat":41.916532,"count":51},
                    {"lng":123.419787,"lat":41.930658,"count":15},
                    {"lng":123.418455,"lat":41.920921,"count":40},
                    {"lng":123.418843,"lat":41.915516,"count":100},
                    {"lng":123.42546,"lat":41.918503,"count":6},
                    {"lng":123.423289,"lat":41.919989,"count":18},
                    {"lng":123.418162,"lat":41.915051,"count":80},
                    {"lng":123.422039,"lat":41.91782,"count":11},
                    {"lng":123.41387,"lat":41.917253,"count":7},
                    {"lng":123.41773,"lat":41.919426,"count":42},
                    {"lng":123.421107,"lat":41.916445,"count":4},
                    {"lng":123.417521,"lat":41.917943,"count":27},
                    {"lng":123.419812,"lat":41.920836,"count":23},
                    {"lng":123.420682,"lat":41.91463,"count":60},
                    {"lng":123.415424,"lat":41.924675,"count":8},
                    {"lng":123.419242,"lat":41.914509,"count":15},
                    {"lng":123.422766,"lat":41.921408,"count":25},
                    {"lng":123.421674,"lat":41.924396,"count":21},
                    {"lng":123.427268,"lat":41.92267,"count":1},
                    {"lng":123.417721,"lat":41.920034,"count":51},
                    {"lng":123.412456,"lat":41.92667,"count":7},
                    {"lng":123.420432,"lat":41.919114,"count":11},
                    {"lng":123.425013,"lat":41.921611,"count":35},
                    {"lng":123.418733,"lat":41.931037,"count":22},
                    {"lng":123.419336,"lat":41.931134,"count":4},
                    {"lng":123.413557,"lat":41.923254,"count":5},
                    {"lng":123.418367,"lat":41.92943,"count":3},
                    {"lng":123.424312,"lat":41.919621,"count":100},
                    {"lng":123.423874,"lat":41.919447,"count":87},
                    {"lng":123.424225,"lat":41.923091,"count":32},
                    {"lng":123.417801,"lat":41.921854,"count":44},
                    {"lng":123.417129,"lat":41.928227,"count":21},
                    {"lng":123.426426,"lat":41.922286,"count":80},
                    {"lng":123.421597,"lat":41.91948,"count":32},
                    {"lng":123.423895,"lat":41.920787,"count":26},
                    {"lng":123.423563,"lat":41.921197,"count":17},
                    {"lng":123.417982,"lat":41.922547,"count":17},
                    {"lng":123.426126,"lat":41.921938,"count":25},
                    {"lng":123.42326,"lat":41.915782,"count":100},
                    {"lng":123.419239,"lat":41.916759,"count":41},
                    {"lng":123.417185,"lat":41.929123,"count":11},
                    {"lng":123.417237,"lat":41.927518,"count":9},
                    {"lng":123.417784,"lat":41.915754,"count":47},
                    {"lng":123.420193,"lat":41.917061,"count":52},
                    {"lng":123.422735,"lat":41.915619,"count":100},
                    {"lng":123.418495,"lat":41.915958,"count":46},
                    {"lng":123.416292,"lat":41.931166,"count":9},
                    {"lng":123.419916,"lat":41.924055,"count":8},
                    {"lng":123.42189,"lat":41.921308,"count":11},
                    {"lng":123.413765,"lat":41.929376,"count":3},
                    {"lng":123.418232,"lat":41.920348,"count":50},
                    {"lng":123.417554,"lat":41.930511,"count":15},
                    {"lng":123.418568,"lat":41.918161,"count":23},
                    {"lng":123.413461,"lat":41.926306,"count":3},
                    {"lng":123.42232,"lat":41.92161,"count":13},
                    {"lng":123.4174,"lat":41.928616,"count":6},
                    {"lng":123.424679,"lat":41.915499,"count":21},
                    {"lng":123.42171,"lat":41.915738,"count":29},
                    {"lng":123.417836,"lat":41.916998,"count":99},
                    {"lng":123.420755,"lat":41.928001,"count":10},
                    {"lng":123.414077,"lat":41.930655,"count":14},
                    {"lng":123.426092,"lat":41.922995,"count":16},
                    {"lng":123.41535,"lat":41.931054,"count":15},
                    {"lng":123.413022,"lat":41.921895,"count":13},
                    {"lng":123.415551,"lat":41.913373,"count":17},
                    {"lng":123.421191,"lat":41.926572,"count":1},
                    {"lng":123.419612,"lat":41.917119,"count":9},
                    {"lng":123.418237,"lat":41.921337,"count":54},
                    {"lng":123.423776,"lat":41.921919,"count":26},
                    {"lng":123.417694,"lat":41.92536,"count":17},
                    {"lng":123.415377,"lat":41.914137,"count":19},
                    {"lng":123.417434,"lat":41.914394,"count":43},
                    {"lng":123.42588,"lat":41.922622,"count":27},
                    {"lng":123.418345,"lat":41.919467,"count":8},
                    {"lng":123.426883,"lat":41.917171,"count":3},
                    {"lng":123.423877,"lat":41.916659,"count":34},
                    {"lng":123.415712,"lat":41.915613,"count":14},
                    {"lng":123.419869,"lat":41.931416,"count":12},
                    {"lng":123.416956,"lat":41.925377,"count":11},
                    {"lng":123.42066,"lat":41.925017,"count":38},
                    {"lng":123.416244,"lat":41.920215,"count":91},
                    {"lng":123.41929,"lat":41.915908,"count":54},
                    {"lng":123.422116,"lat":41.919658,"count":21},
                    {"lng":123.4183,"lat":41.925015,"count":15},
                    {"lng":123.421969,"lat":41.913527,"count":3},
                    {"lng":123.422936,"lat":41.921854,"count":24},
                    {"lng":123.41905,"lat":41.929217,"count":12},
                    {"lng":123.424579,"lat":41.914987,"count":57},
                    {"lng":123.42076,"lat":41.915251,"count":70},
                    {"lng":123.425867,"lat":41.918989,"count":8}
                ],
                map: '',// 保存地图实例
                centerLng: '123.418261', // 经度
                centerLat: '41.921984', // 纬度
                heatmapOverlay: {},// 热力图覆盖物
            }
        },
        methods: {
            // 创建和初始化地图函数
            initMap(){
                this.createMap();// 创建地图
                this.initHeatMap();// 添加热力图覆盖物
            },
            // 方法 - 创建地图
            createMap(){
                // 在百度地图容器中创建地图实例
                let map = new BMap.Map("container");
                // 将map变量存储在全局
                this.map = map;
                // 设定地图的中心点和坐标
                let point = new BMap.Point(this.centerLng, this.centerLat);
                // 设置中心点坐标和地图级别
                this.map.centerAndZoom(point, 15);
                // 允许滚轮缩放
                this.map.enableScrollWheelZoom(point, 15);
                // 添加左上角缩放比例尺(offset: new BMap.Size(0, 0)为比例尺的坐标位置)
                var opts = {offset: new BMap.Size(10, 10)}
                this.map.addControl(new BMap.NavigationControl(opts));
                // 设置地图默认缩放比例
                this.map.setZoom(15);
            },
            // 方法 - 添加热力图覆盖物
            initHeatMap () {
                this.heatmapOverlay = new BMapLib.HeatmapOverlay({
                    // 热力图的每个点的半径大小
                    'radius': BMAP_POINT_SIZE_SMALL * 4,
                    // 热力的透明度0~1
                    'opacity': 0.8,
                    // 其中 key 表示插值的位置0~1，value 为颜色值
                    'gradient': {
                        0:'rgb(102, 255, 0)',
                        .5:'rgb(255, 170, 0)',
                        1:'rgb(255, 0, 0)'
                    }
                })
                // 清除图层(每次重新调用需要清除上一个覆盖物图层)
                this.map.clearOverlays();
                // 添加热力覆盖物
                this.map.addOverlay(this.heatmapOverlay);
                this.heatmapOverlay.setDataSet({data: this.points, max: 100});
                // 显示热力图，隐藏为this.heatmapOverlay.hide();
                this.heatmapOverlay.show();
            }
        },
        mounted() {
            // 创建和初始化地图函数
            this.initMap();
        }
    }
</script>

<style >
    #load {
        width: 100%;
        height: 430px;
    }
    #container {
        width: 100%;
        height: 430px;
        border: #ccc solid 1px;
    }
</style>