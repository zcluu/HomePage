<template>
    <div class="bg-img">
        <div class="center-box">
            <el-avatar :src="this.$_avatar" :size="160" style="background-color: #fff;"></el-avatar>
            <div class="name">This is ZCLU !</div>
            <div class="title">
                <div :class="{blink:full}" class="blink-text" :style="{padding:'1rem 0'}">
                    <template v-for="item in items" :key="item">
                        {{ item }}
                    </template>
                </div>
            </div>
        </div>
        <a @click="smooth('about')" class="btn-next">
            <el-icon style="transform: rotate(90deg)" :size="50">
                <DArrowRight/>
            </el-icon>
        </a>
    </div>
</template>

<script>
import {defineComponent} from "vue";
import {DArrowRight} from "@element-plus/icons-vue";

export default defineComponent({
    name: "bg-page",
    components: {DArrowRight},
    data() {
        const items = []
        return {
            titles: [
                '浙大硕士在读 技术至上',
                '地道山东人 豪爽且务实',
                '独立开发者 代码即信仰',
                '执着于打造 “无懈可击”的Bug',
            ],
            index: 0,
            items: items,
            timer: 0,
            full: false,
            lineColor: '#9f2c00'
        }
    },
    setup() {
        return {}
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
        smooth(id) {
            this.$_smooth(id)
        }
    },
    mounted() {
        this.timer = setInterval(this.blink, 300)
    }
})
</script>

<style lang="less" scoped>
@img: '../assets/img/';
@lineColor: #f17c67;
.bg-img {
  position: relative;
  height: 100vh;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  background-image: url(/static/bg.png);
  background-size: cover;
  background-position: center;

  .btn-next {
    position: absolute;
    bottom: 20px;
    animation: bounce infinite 1.5s;
    color: #fff;
  }
}

.center-box {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

.name {
  color: #fff;
  font-size: 2rem;
  margin: 2rem 0 1.5rem;
  font-weight: bold;
}

.title {
  margin: 0 0 1.5rem;
  color: #fff;
  font-size: 1.5rem;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 8rem;

  .blink-text {
    border-right: 5px solid @lineColor;
    animation: twink 1s infinite;
  }
}

.blink {
  background-color: @lineColor !important;
  border-right-color: @lineColor !important;
}

@keyframes twink {
  50% {
    border-right-color: transparent;
  }
}

@keyframes bounce {
  0%, 20% {
    animation-timing-function: cubic-bezier(0.215, 0.610, 0.355, 1.000);
    transform: translate3d(0, 0, 0);
  }

  40%, 43% {
    animation-timing-function: cubic-bezier(0.755, 0.050, 0.855, 0.060);
    transform: translate3d(0, -30px, 0);
  }

  53% {
    animation-timing-function: cubic-bezier(0.215, 0.610, 0.355, 1.000);
    transform: translate3d(0, 0, 0);
  }

  70% {
    animation-timing-function: cubic-bezier(0.755, 0.050, 0.855, 0.060);
    transform: translate3d(0, -15px, 0);
  }

  80% {
    animation-timing-function: cubic-bezier(0.215, 0.610, 0.355, 1.000);
    transform: translate3d(0, 0, 0);
  }

  90% {
    transform: translate3d(0, -8px, 0);
  }

  100% {
    animation-timing-function: cubic-bezier(0.215, 0.610, 0.355, 1.000);
    transform: translate3d(0, 0, 0);
  }

}
</style>