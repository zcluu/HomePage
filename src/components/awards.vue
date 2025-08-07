<script>
import {defineComponent} from 'vue'
import BaseComponent from "@/components/baseComponent.vue";

export default defineComponent({
    name: "awards",
    components: {BaseComponent}
})
</script>

<script setup>
let items = [
    {
        title: '全国高校计算机能力挑战赛C++全国一等奖',
        src: '/static/awards/cpp.jpeg',
    },
    {
        title: '全国高校计算机能力挑战赛Python全国二等奖',
        src: '/static/awards/python.jpeg',
    },
    {
        title: '团体程序设计天梯赛个人全国二等奖(全校最高分)',
        src: '/static/awards/tts1.png',
    },
    {
        title: '团体程序设计天梯赛团队全国三等奖',
        src: '/static/awards/tts2.png',
    },
    {
        title: '蓝桥杯全国软件和信息技术专业人才大赛全国三等奖',
        src: '/static/awards/lqb.jpg',
    },
    {
        title: '中国大学生服务外包创新创业大赛华东三等奖',
        src: '/static/awards/fwwb.jpg',
    },
    {
        title: '中国大学生计算机设计大赛山东省三等奖',
        src: '/static/awards/jsjsjds.jpg',
    },
]
</script>

<template>
    <base-component
            sub_title="AWARDS"
            main_title="COMPETITION AWARDS"
            id="awards"
            :is-white="true"
    >
        <template #mainBox>
            <el-collapse
                accordion
            >
                <el-collapse-item
                        v-for="item in items"
                        :title="item.title"
                >
                    <el-image :src="item.src"
                              style="width: auto; height: 450px; margin: 0px 5%;"
                    ></el-image>
                </el-collapse-item>
            </el-collapse>
        </template>
    </base-component>
</template>

<style scoped lang="less">

</style>