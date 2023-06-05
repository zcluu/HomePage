<template>
  <div id="top" class="avatar">
    <el-avatar
        :src="$_avatar"
        :size="80"
        style="background-color: #fff;"
    ></el-avatar>
    <span class="name">
    山财大鲁兆成
  </span>
  </div>
  <div class="menu">
    <el-row class="menu-item" @click="jump(item.href)" v-for="item in items" :key="item">
      <el-col :span="3" style="display:flex;align-items: flex-start;">
          <el-icon style="font-size: 14px; --color: #888; margin-top: 0.3rem;">
              <House v-if="item.icon==='home'"/>
              <User v-if="item.icon==='user'"/>
              <Postcard v-if="item.icon==='introduce'"/>
              <id-card v-if="item.icon==='idcard'"/>
              <Medal v-if="item.icon==='awards'"/>
              <PieChart v-if="item.icon==='scientific'"/>
              <Camera v-if="item.icon==='photo'"/>
              <Cpu v-if="item.icon==='stack'"/>
              <Message v-if="item.icon==='contact'"/>
          </el-icon>
      </el-col>
      <el-col :span="12">
        <el-link href="">{{ item.title }}</el-link>
      </el-col>
    </el-row>
  </div>
</template>

<script>
import {defineComponent} from "vue";
import {Camera, Cpu, HomeFilled, House, Medal, Message, PieChart, Postcard, User} from "@element-plus/icons-vue";
import IdCard from "@/components/icon/idCard.vue";

export default defineComponent({
  name: "side",
    components: {Message, Cpu, Camera, PieChart, Medal, IdCard, Postcard, User, House, HomeFilled},
  data() {
    return {
      items: [
        {icon: 'home', title: '首页', href: 'top'},
        {icon: 'user', title: '关于', href: 'about'},
        {icon: 'introduce', title: '介绍', href: 'introduction'},
        {icon: 'idcard', title: '经历', href: 'experience'},
        {icon: 'awards', title: '竞赛', href: 'awards'},
        {icon: 'scientific', title: '科研', href: 'scientific'},
        {icon: 'photo', title: '剪影', href: 'photo'},
        {icon: 'stack', title: '技术栈', href: 'stack'},
        {icon: 'contact', title: '联系我', href: 'contact'},
      ]
    }
  },
  methods: {
    jump(id) {
      this.$_smooth(id)
    }
  }
})
</script>
<style lang="less" scoped>
.avatar {
  width: 100%;
  height: 200px;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;

  .name {
    margin-top: 12px;
    font-size: 1.05rem;
    color: #888;
  }
}

.menu {
  width: 100%;

  .menu-item {
    list-style: none;
    padding: 20px 15px 10px;
    width: 90%;
    margin: 0 auto;
    border-bottom: 1px dotted #888888;
    font-size: .9rem;

    a {
      color: #888;
      text-decoration: none;
    }
  }
}
</style>