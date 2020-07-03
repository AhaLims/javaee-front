<template>
    <div>
        <div class="crumbs">
            <el-breadcrumb separator="/">
                <el-breadcrumb-item>
                    <i class="el-icon-pie-chart"></i> schart图表
                </el-breadcrumb-item>
            </el-breadcrumb>
        </div>
        <div class="container">
            <div class="plugins-tips">
                vue-schart：vue.js封装sChart.js的图表组件。
                访问地址：
                <a
                    href="https://github.com/lin-xin/vue-schart"
                    target="_blank"
                >vue-schart</a>
            </div>
            <div class="schart-box">
                <div class="content-title">柱状图</div>
                <schart class="schart" canvasId="city-bar" :options="options1"></schart>
            </div>
            <div class="schart-box">
                <div class="content-title">折线图</div>
                <schart class="schart" canvasId="line" :options="options2"></schart>
            </div>
            <div class="schart-box">
                <div class="content-title">饼状图</div>
                <schart class="schart" canvasId="pie" :options="options3"></schart>
            </div>
            <div class="schart-box">
                <div class="content-title">环形图</div>
                <schart class="schart" canvasId="ring" :options="options4"></schart>
            </div>
            <div class="schart-box">
                <div class="content-title">another</div>
                <schart class="schart" canvasId="ring" :options="options5"></schart>
            </div>
        </div>
    </div>
</template>

<script>
import Schart from 'vue-schart';
export default {
    name: 'basecharts',
    components: {
        Schart
    },
    data() {
        return {
            options1: {
                type: 'bar',
                title: {
                    text: '截至目前为止，现存新冠肺炎的年龄分布'
                },
                bgColor: '#fbfbfb',
                labels: ['0-10', '11-20', '21-30', '31-40', '41-50','51-60','60及以上'],
                datasets: [
                    {
                        label: '患病人数',
                        fillColor: 'rgba(241, 49, 74, 0.5)',
                        data: [13,23,434,52,62,73,33] //这个data应该是要与后端交互的
                    },
                    {
                        label: '本地病例',
                        data: [1, 28, 2, 190, 230,11,12,457,156,11,45,612]
                    },
                    {
                        label: '输入病例',
                        data: [1, 28, 2, 190, 230,11,12,457,156,11,45,612]
                    },
                ]
            },
            options2: {
                type: 'line',
                title: {
                    text: '全省新增确诊'
                },
                bgColor: '#fbfbfb',
                labels: ['04-21', '04-24', '04-27', '04-30', '05-03'],
                datasets: [
                    {
                        label: '当日总新增',
                        data: [234, 278, 270, 190, 230,11,12,457,156,11,45,612]
                    },


                ]
            },
            options3: {
                type: 'pie',
                title: {
                    text: '病人性别比例'
                },
                legend: {
                    position: 'left'
                },
                bgColor: '#fbfbfb',
                labels: ['男性', '女性'],
                datasets: [
                    {
                        data: [334, 278]
                    }
                ]
            },
            options4: {
                type: 'bar',
                title: {
                    text: '本地病例以及外地输入病例'
                },
                showValue: false,
                legend: {
                    position: 'bottom',
                    bottom: 40
                },
                bgColor: '#fbfbfb',
                labels: ['本地病例', '外地输入病例'],
                datasets: [
                    {
                        data: [500, 100]
                    }
                ]
            },
            options5: {
                type: 'ring',
                title: {
                    text: '目前情况'
                },
                showValue: false,
                legend: {
                    position: 'bottom',
                    bottom: 40
                },
                bgColor: '#fbfbfb',
                labels: ['确诊病例', '疑似患者', '无症状感染者','密切接触者','健康隔离者'],
                datasets: [
                    {
                        data: [50, 60, 70,80,90]
                    }
                ]
            }
        };
    }
};
</script>

<style scoped>
.schart-box {
    display: inline-block;
    margin: 20px;
}
.schart {
    width: 600px;
    height: 400px;
}
.content-title {
    clear: both;
    font-weight: 400;
    line-height: 50px;
    margin: 10px 0;
    font-size: 22px;
    color: #1f2f3d;
}
</style>