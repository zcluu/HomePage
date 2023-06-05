<template>
    <div class="main" :id="id"
         :style="{backgroundColor: isWhite?'#fff':'rgb(247, 247, 247)',padding:$_isMobile()?'20px':'35px'}"
    >
        <div class="title">
            <el-row>
                <span class="subtitle">{{ sub_title }}</span>
            </el-row>
            <el-row>
                <span class="main-title">{{ main_title }}</span>
            </el-row>
        </div>
        <div class="box" :style="{padding: $_isMobile()?'1rem':'2rem'}">
            <slot name="mainBox"/>
        </div>
    </div>
</template>
<script>
import {defineComponent} from 'vue'

export default defineComponent({
    name: "baseComponent",
    props: ['id', 'main_title', 'sub_title', 'isWhite']
})
</script>

<style lang="less" scoped>
.title {
  border-left: 6px solid #e3872d;
  padding: .6rem 0 .6rem 2rem;

  .subtitle {
    font-size: .8rem;
    color: #888888;
    letter-spacing: .4rem;
    margin-bottom: 0.5rem;
  }

  .main-title {
    font-size: 2rem;
    letter-spacing: .2rem;
  }
}

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

  .line {
    width: 5px;
    padding: 1.65rem 0;
    display: inline-block;
    animation: twink 1s infinite;
  }
}

.blink {
  background-color: @lineColor !important;
  color: #fff;
}

@keyframes twink {
  50% {
    background-color: @lineColor;
  }
}
</style>