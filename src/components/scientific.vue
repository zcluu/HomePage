<script>
import {defineComponent} from 'vue'
import BaseComponent from "@/components/baseComponent.vue";

export default defineComponent({
    name: "scientific",
    components: {BaseComponent}
})
</script>

<template>
    <base-component
            sub_title="SCIENTIFIC"
            main_title="SCIENTIFIC RESEARCH"
            id="scientific"
    >
        <template #mainBox>
            <el-row :gutter="$_isMobile()?0:80">
                <el-col :xs="24" :sm="24" :lg="12" :span="12"
                        :style="{marginBottom:$_isMobile()?'20px':'0'}"
                >
                    <el-card
                            header="基于 Resnet+LSTM 实现的行为识别"
                    >
                        <el-carousel
                                arrow="never"
                                indicator-position="none"
                                :height="$_isMobile()?'170px':'300px'"
                                :pause-on-hover="false"
                        >
                            <el-carousel-item
                                    v-for="ix in 3"
                                    style="display: flex;justify-content: center;align-items: center;"
                            >
                                <el-image
                                        :src="'http://oss.py00.cn/blog/scientific-research/1_'+ix+'.png'"
                                        style="height: 100%;"
                                ></el-image>
                            </el-carousel-item>
                        </el-carousel>
                        <el-space direction="vertical"
                                  style="align-items: start;font-size: var(--el-font-size-base);word-break: break-all;padding: 10px 10px 0px;"
                        >
                            <span>采用 CNN-LSTM 的方法实现五种行为识别分类</span>
                            <span>采用 Resnet50 进行网络特征提取</span>
                            <span>使用 Attention-LSTM 实现时间维度上的特征连接</span>
                            <span>改用 Mish 激活函数和 Ranger 优化器</span>
                            <span>对比模型参照 C3D、3DResnet、3DDensenet、Resnet-LSTM 等</span>
                            <span>
                                <el-link href="https://doi.org/10.1016/j.compag.2022.107404">
                                    https://doi.org/10.1016/j.compag.2022.107404
                                </el-link>
                            </span>
                        </el-space>
                    </el-card>
                </el-col>
                <el-col :xs="24" :sm="24" :lg="12" :span="12">
                    <el-card
                            header="YOLO-R: 基于 YOLOv5 的加强版实时目标检测"
                    >
                        <el-carousel
                                arrow="never"
                                indicator-position="none"
                                :height="$_isMobile()?'170px':'300px'"
                                :pause-on-hover="false"
                        >
                            <el-carousel-item
                                    v-for="ix in 4"
                            >
                                <el-image
                                        :src="'http://oss.py00.cn/blog/scientific-research/3_'+ix+'.jpg'"
                                        style="height: 100%;"
                                ></el-image>
                            </el-carousel-item>
                        </el-carousel>
                        <el-space direction="vertical"
                                  style="align-items: start;font-size: var(--el-font-size-base);word-break: break-all;padding: 10px 10px 0px;"
                        >
                            <span>baseline 采用 YOLOv5l</span>
                            <span>消融实验验证实验改进的可行性</span>
                            <span>SPPF模块替换为RFB模块，通过增加网络模型的接受域来增强网络的特征提取能力</span>
                            <span>FPN部分增加了两个快捷连接，增强了特性的可重用性，减少了有用信息的丢失</span>
                            <span>在网络的PAN部分增加了三个CBAM注意机制模块，忽略复杂干扰因素的影响</span>
                            <span>
                                <el-link href="https://doi.org/10.1016/j.compag.2023.107639">
                                    https://doi.org/10.1016/j.compag.2023.107639
                                </el-link>
                            </span>
                        </el-space>
                    </el-card>
                </el-col>
            </el-row>
        </template>
    </base-component>
</template>

<style scoped lang="less">

</style>