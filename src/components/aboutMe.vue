<script>
import {defineComponent} from 'vue'
import BaseComponent from "@/components/baseComponent.vue";

export default defineComponent({
    name: "aboutMe",
    components: {BaseComponent},
    data() {
        const items = []
        return {
            titles: [
                '浙大硕士在读',
                '学习编程十年有余',
                '全能码农，全栈开发',
                '阅码无数，心中无码',
            ],
            index: 0,
            items: items,
            timer: 0,
            full: false,
            lineColor: '#9f2c00',
        }
    },
    methods: {
        blink: function () {
            let len = this.items.length
            this.items.push(this.titles[this.index][len])
            if (len + 1 === this.titles[this.index].length) {
                clearInterval(this.timer)
                setTimeout(() => {
                    this.full = true
                }, 1000)
                setTimeout(() => {
                    this.full = false
                    this.timer = setInterval(this.blink, 300)
                    this.items = []
                    this.index = (this.index + 1) % this.titles.length
                }, 1200)
            }
        },
    },
    mounted() {
        this.timer = setInterval(this.blink, 300)
    }
})
</script>

<template>
    <base-component
            id="about"
            sub_title="INFORMATION"
            main_title="ABOUT ME"
    >
        <template #mainBox>
            <el-row :gutter="20" style="margin-left: -20px; margin-right: -20px;">
                <el-col :lg="6" :md="12" :xs="24" style="padding-left: 20px; padding-right: 20px;text-align: center;">
                    <el-image
                            :z-index="9999"
                            :src="$_avatar"
                            style="height: 14rem;"
                    ></el-image>
                </el-col>
                <el-col :lg="16" :md="12" :xs="24">
                    <span class="content-title">ABOUT ME</span>
                    <div class="blink-title">
                        <div style="display: inline-block;height: 2rem;line-height: 2rem;">鲁兆成，</div>
                        <div :class="{blink:full}" class="blink-text" :style="{display:'inline-block'}"
                             style="height: 2rem;line-height: 2rem;"
                        >
                            <template v-for="item in items" :key="item">
                                {{ item }}
                            </template>
                        </div>
                    </div>
                    <p class="content">
                        生于山东，纯北方汉子，毕业于济南山财大，现求学于浙江大学~<br>
                      『<b>克明峻德，格物致知</b>』这是母校给予的八字真言，良师益友收获颇多~<br>
                        科班出身，钻研编程近十年，上能科研，下能软开，在研Model Language<br>
                        熬过大夜，竭力奋斗，终成正果，稳步向前，论文一二，语言伍六七，框架七八个，作品十七八<br>
                        累哉累哉，苦中作乐，低头苦干，只管耕耘，亦可收获颇丰！最大目标，无所拘束，做我想做~
                    </p>
                </el-col>
            </el-row>
        </template>
    </base-component>
</template>

<style scoped lang="less">
.content-title {
  color: #888;
  letter-spacing: 5px;
  text-transform: uppercase;
  padding-bottom: 1rem;
}

.content {
  line-height: 2rem;
}

@lineColor: #f69c8e;

.blink-title {
  margin: 1.1rem 0 0;
  color: #000;
  display: flex;
  justify-content: left;
  align-items: center;

  .blink-text {
    border-right: 5px solid @lineColor;
    animation: twink 1s infinite;
  }
}

.blink {
  background-color: @lineColor !important;
  border-right-color: @lineColor !important;
  color: #fff;
}

@keyframes twink {
  50% {
    border-right-color: transparent;
  }
}
</style>