<template>
    <div class="panel leftone">
        <h2>关键词排行榜</h2>
        <div class="chart" ref="leftone"></div>
        <div class="panel-footer"></div>
    </div>
  
</template>

<script>
export default {
    name: '',
    data(){
        return{
            
        }
    },
    mounted(){
        this.$nextTick(()=>{
            this.init()
        })
    },
    methods:{
        init(){
           // 基于准备好的dom，初始化echarts实例
            var myChart = echarts.init(this.$refs.leftone);

            var data = [90, 80, 75, 65, 65];
            var titlename = ["javascript", "VUE", "jQuery", "HTML5", "CSS3"];
            var valdata = ["精通", "熟练", "熟练", "掌握", "掌握"];
            var myColor = ["#1089E7", "#F57474", "#56D0E3", "#F8B448", "#8B78F6"];
            var option = {
                //图标位置
                grid: {
                top: "10%",
                left: "22%",
                bottom: "10%"
                },
                xAxis: {
                show: false
                },
                yAxis: [
                {
                    show: true,
                    data: titlename,
                    inverse: true,
                    axisLine: {
                    show: false
                    },
                    splitLine: {
                    show: false
                    },
                    axisTick: {
                    show: false
                    },
                    axisLabel: {
                    color: "#fff",

                    rich: {
                        lg: {
                        backgroundColor: "#339911",
                        color: "#fff",
                        borderRadius: 15,
                        // padding: 5,
                        align: "center",
                        width: 15,
                        height: 15
                        }
                    }
                    }
                },
                {
                    show: false,
                    inverse: true,
                    data: valdata,
                    axisLabel: {
                    textStyle: {
                        fontSize: 12,
                        color: "#fff"
                    }
                    }
                }
                ],
                series: [
                {
                    name: "条",
                    type: "bar",
                    yAxisIndex: 0,
                    data: data,
                    barCategoryGap: 50,
                    barWidth: 10,
                    itemStyle: {
                    normal: {
                        barBorderRadius: 20,
                        color: function (params) {
                        var num = myColor.length;
                        return myColor[params.dataIndex % num];
                        }
                    }
                    },
                    label: {
                    normal: {
                        show: true,
                        position: "inside",
                        formatter: "{c}%"
                    }
                    }
                },
                {
                    name: "框",
                    type: "bar",
                    yAxisIndex: 1,
                    barCategoryGap: 50,
                    data: [100, 100, 100, 100, 100],
                    barWidth: 15,
                    itemStyle: {
                    normal: {
                        color: "none",
                        borderColor: "#00c1de",
                        borderWidth: 3,
                        barBorderRadius: 15
                    }
                    }
                }
                ]
            };

            // 使用刚指定的配置项和数据显示图表。
            myChart.setOption(option);
            window.addEventListener("resize", function () {
                myChart.resize();
            });
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="less">

</style>