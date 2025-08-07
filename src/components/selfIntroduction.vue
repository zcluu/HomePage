<script>
import {defineComponent} from 'vue'
import BaseComponent from "@/components/baseComponent.vue";

export default defineComponent({
    name: "selfIntroduction",
    components: {BaseComponent}
})
</script>

<template>
    <base-component
            sub_title="INTRODUCTION"
            main_title="SELF INTRODUCTION"
            id="introduction"
            :is-white="true"
    >
        <template #mainBox>
            <el-row :gutter="5">
                <el-col
                        :span="14"
                        :sm="15"
                        :xs="24"
                >
                    <el-descriptions direction="horizontal" column="1">
                        <el-descriptions-item label="政治面貌">共青团员</el-descriptions-item>
                        <el-descriptions-item label="成绩情况">综合测评1/99，综合绩点4.22/5</el-descriptions-item>
                        <el-descriptions-item label="等级考试">英语四六级、计算机二三级</el-descriptions-item>
                        <el-descriptions-item label="在校荣誉">
                            校优秀学生、校优秀团员、2021年度山东省优秀学生、2023届山东省优秀毕业生
                        </el-descriptions-item>
                        <el-descriptions-item label="在校奖金">
                            校一等奖学金、校单项奖学金、2021年度校长奖学金、2022年度国家奖学金
                        </el-descriptions-item>
                        <el-descriptions-item label="职业认证">
                            工业互联网平台开发工程师(中级)、低代码开发师、数字化会计师、数字化管理师等
                        </el-descriptions-item>
                    </el-descriptions>
                </el-col>
                <el-col
                        :span="10"
                        :sm="9"
                        :xs="24"
                >
                    <el-carousel
                            arrow="never"
                            direction="vertical"
                            indicator-position="none"
                            height="14rem"
                    >
                        <el-carousel-item v-for="ix in 7"
                                          style="display: flex; justify-content: center; align-items: center;"
                        >
                            <el-image
                                    style="height: 100%;"
                                    :src="'/static/introduction/'+ix+'.jpg'"
                            ></el-image>
                        </el-carousel-item>
                    </el-carousel>
                </el-col>
            </el-row>
        </template>
    </base-component>
</template>

<style scoped lang="less">

</style>