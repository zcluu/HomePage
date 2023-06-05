<template>
  <div class="main">
    <div class="title">
      <el-row>
        <span class="subtitle">BLOG</span>
      </el-row>
      <el-row>
        <span class="maintitle">LATEST BLOG</span>
      </el-row>
    </div>
    <div v-for="item in items" :key="item" class="item">
      <el-row class="row-1">
        <el-col :lg="1" :sm="2" :xs="3">
        <span class="icon">
          <el-icon color="#fff">
            <i aria-label="icon: book" class="anticon anticon-book"><svg viewBox="64 64 896 896" data-icon="book"
                                                                         width="1em" height="1em" fill="currentColor"
                                                                         aria-hidden="true" focusable="false" class=""><path
                d="M832 64H192c-17.7 0-32 14.3-32 32v832c0 17.7 14.3 32 32 32h640c17.7 0 32-14.3 32-32V96c0-17.7-14.3-32-32-32zm-260 72h96v209.9L621.5 312 572 347.4V136zm220 752H232V136h280v296.9c0 3.3 1 6.6 3 9.3a15.9 15.9 0 0 0 22.3 3.7l83.8-59.9 81.4 59.4c2.7 2 6 3.1 9.4 3.1 8.8 0 16-7.2 16-16V136h64v752z"></path></svg></i>
          </el-icon>
        </span>
        </el-col>
        <el-col :sm="22" :xs="21">
          <el-row>
          <span class="item-title">
            {{item.title}}
          </span>
          </el-row>
          <el-row>
            <div class="description">
              <a style="margin-right: .3rem;" class="author">林舍</a>
              <span style="margin-right: .3rem;" class="time">2020-08-06 08:59:06</span>
              <el-tag style="margin-right: .3rem;" type="info" effect="plain"
                      size="small"
              >1
              </el-tag>
              <el-tag>2</el-tag>
            </div>
          </el-row>
        </el-col>
      </el-row>
      <el-row>00</el-row>
    </div>
  </div>
</template>

<script lang="ts">
import {defineComponent} from "vue";

export default defineComponent({
  name: "Blog",
  data() {
    return {}
  }
})
</script>
<script lang="ts" setup>
import {getCurrentInstance, ref} from "vue";
let items = ref('');
const {ctx, proxy} = getCurrentInstance();
proxy.$axios.get('/get/content/all').then((res)=>{
  console.log(res.data)
  items = res.data.data
})
</script>


<style lang="less" scoped>
.title {
  border-left: 6px solid #e3872d;
  padding: .6rem 0 .6rem 2rem;
  margin-bottom: 3rem;

  .subtitle {
    font-size: .8rem;
    color: #888888;
    letter-spacing: .4rem;
    margin-bottom: 0.5rem;
  }

  .maintitle {
    font-size: 2rem;
    letter-spacing: .2rem;
  }
}

.item {
  color: rgba(0, 0, 0, 0.65);

  .icon {
    display: inline-block;
    text-align: center;
    margin: 0 auto;
    width: 32px;
    height: 32px;
    line-height: 32px;
    background-color: rgba(241, 124, 103, .99);
    border-radius: 50%;
  }

  .row-1 {
    margin-bottom: .6rem;
  }

  .item-title {
  }

  .description {
    margin-top: 1rem;
    height: 2rem;
    line-height: 2rem;
    font-size: 14px;

    .author {
      color: var(--el-color-primary-light-1);
      transition-duration: .4s;

      &:hover {
        color: var(--el-color-primary-light-4);
      }
    }
  }
}
</style>