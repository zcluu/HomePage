<script>
import {defineComponent} from 'vue'
import BaseComponent from "@/components/baseComponent.vue";

export default defineComponent({
    name: "stack",
    components: {BaseComponent}
})
</script>
<script setup>
let items = [
    {
        title: '前端：Vue、React、Uniapp、ElementUI等',
        percentage: '85'
    },
    {
        title: '后端：Django、Flask、FastAPI、Gin、SpringBoot、Nginx等',
        percentage: '95'
    },
    {
        title: '移动端：Android、ReactNative、Harmony',
        percentage: '93'
    },
    {
        title: '数据库：MySQL、SQLite、PostgreSQL、Redis、Mybatis等',
        percentage: '97'
    },
    {
        title: '微服务：SpringCloud、Nacos、Feign、Sentinel等',
        percentage: '89'
    },
    {
        title: '大数据：Hadoop、Spark、PySpark、Zookeeper、Hive等',
        percentage: '88'
    },
    {
        title: '深度学习：Pytorch、PaddlePaddle、Jittor、MMAction2、MMDetection等',
        percentage: '95'
    },
    {
        title: '数据可视化：Echart、PowerBI',
        percentage: '85'
    },
    {
        title: '云计算：Docker、Docker Compose',
        percentage: '88'
    },
    {
        title: '其他：Git、SVN、Crawler、Socket、Re、Pycharm、Load Balance等',
        percentage: '91'
    },
]
const customColor = '#409eff'
const customColors = [
    { color: '#f56c6c', percentage: 60 },
    { color: '#f56c6c', percentage: 85 },
    { color: '#e6a23c', percentage: 90 },
    { color: '#5cb87a', percentage: 95 },
    { color: '#1989fa', percentage: 100 },
]
</script>

<template>
    <base-component
            id="stack"
            sub_title="FULL STACK"
            main_title="TECHNOLOGY STACK"
    >
        <template #mainBox>
            <div v-for="item in items" style="padding-bottom: 20px;">
                <el-link>{{ item.title }}</el-link>
                <el-progress
                        :percentage="item.percentage"
                        :color="customColors"
                        :show-text="false"
                ></el-progress>
            </div>
        </template>
    </base-component>
</template>

<style scoped lang="less">

</style>