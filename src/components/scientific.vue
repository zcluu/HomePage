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
                            header="Broodstock breeding behaviour recognition based on Resnet50-LSTM with CBAM attention mechanism"
                    >
                        <el-carousel
                                arrow="never"
                                indicator-position="none"
                                :height="$_isMobile()?'170px':'300px'"
                                :pause-on-hover="false"
                        >
                            <el-carousel-item
                                    v-for="ix in 4"
                                    style="display: flex;justify-content: center;align-items: center;"
                            >
                                <el-image
                                        :src="'/static/papers/j.compag.2022.107404/'+ix+'.PNG'"
                                        style="height: 100%;"
                                ></el-image>
                            </el-carousel-item>
                        </el-carousel>
                        <el-space direction="vertical"
                                  style="align-items: start;font-size: var(--el-font-size-base);word-break: break-all;padding: 10px 10px 0px;"
                        >
                            <span>- 采用ResNet50-LSTM架构，实现五类繁殖行为识别，并结合CNN提取时空特征</span>
                            <span>- 通过Attention-LSTM建模时序关系，增强长期依赖捕捉，提高识别精度</span>
                            <span>- 在骨干网络嵌入CBAM模块，增强空间与通道注意力，提高特征表达能力</span>
                            <span>- 使用Mish激活函数替代ReLU，结合Ranger优化器，加速收敛并提升泛化能力</span>
                            <span>- 对比模型参照 C3D、3DResnet、3DDensenet、Resnet-LSTM 等</span>
                            <span>- 进行C3D、3D ResNet、3D DenseNet及ResNet-LSTM对比实验，验证模型有效性</span>
                            <span>
                                <el-link href="https://doi.org/10.1016/j.compag.2022.107404">
                                    DOI: 10.1016/j.compag.2022.107404
                                </el-link>
                            </span>
                        </el-space>
                    </el-card>
                </el-col>
                <el-col :xs="24" :sm="24" :lg="12" :span="12">
                    <el-card
                            header="A novel automatic detection method for breeding behavior of broodstock based on improved YOLOv5"
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
                                        :src="'/static/papers/j.compag.2023.107639/'+ix+'.PNG'"
                                        style="height: 100%;"
                                ></el-image>
                            </el-carousel-item>
                        </el-carousel>
                        <el-space direction="vertical"
                                  style="align-items: start;font-size: var(--el-font-size-base);word-break: break-all;padding: 10px 10px 0px;"
                        >
                            <span>- 针对鱼类夜间繁殖行为监测难题，改进YOLOv5检测方法，提升精度与环境适应性</span>
                            <span>- 将YOLOv5v6.0骨干网络中的SPPF模块替换为RFB，扩大感受野并增强特征提取能力</span>
                            <span>- 在FPN增加残差连接，提高特征重用率，减少信息损失，优化多尺度特征融合</span>
                            <span>- 在PAN嵌入CBAM注意力机制，增强关键行为特征提取，提升检测准确率</span>
                            <span>- 采集并标注红外视频数据集，开展消融与对比实验，验证改进模型的检测性能</span>
                            <span>- 对比Faster R-CNN、EfficientDet、YOLOv5原始版本等目标检测方案，验证模型</span>
                            <span>
                                <el-link href="https://doi.org/10.1016/j.compag.2023.107639">
                                    DOI: 10.1016/j.compag.2023.107639
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