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
            生于山东，地道的北方汉子，本科毕业于济南山财大，现于浙江大学继续求<br>
            『<b>克明峻德，格物致知</b>』——母校赋予的八字箴言，恩师益友，收获良多<br>
            自科班出身，潜心钻研编程近十载，科研与软件开发皆有涉猎，当前专注于~通信AI~研究<br>
            夜以继日，笃行不怠，稳步前行。已发表论文数篇，精通多种语言，熟练掌握多个框架，完成十余项目<br>
            虽劳其身，亦乐在其中。专注耕耘，砥砺前行，愿无所束缚，尽情探索，做自己真正热爱的事！
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