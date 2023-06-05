<script setup>
import AboutMe from "@/components/aboutMe.vue";
import BgPage from "@/components/bg-page.vue";
import {Menu} from "@element-plus/icons-vue";
import Side from "@/components/side.vue";
import SelfIntroduction from "@/components/selfIntroduction.vue";
import Experience from "@/components/Experience.vue";
import Awards from "@/components/awards.vue";
import Scientific from "@/components/scientific.vue";
import MyPhotos from "@/components/myPhotos.vue";
import Stack from "@/components/stack.vue";
import ContactMe from "@/components/contactMe.vue";
</script>
<script>
import {defineComponent} from "vue";

export default defineComponent({
    data() {
        return {
            drawer: false,
            top: false,
        }
    },
    methods: {
        _isMobile() {
            // return this.$_isMobile()
        },
        change(val) {
            this.top = val
        }
    }
})
</script>

<template>
    <div id="top"></div>
    <bg-page></bg-page>
    <el-container id="container" style="position: relative;">
        <el-affix
                @change="change"
                v-if="!$_isMobile()" :z-index="999" id="container" style="
                    background-color: #fff;
                    z-index: 10;">
            <el-aside style="height: 100vh;box-shadow: 0 0 8px rgba(136,136,136,0.53);">
                <side @call="callSon"/>
            </el-aside>
        </el-affix>
        <el-affix
                @change="change"
                offset="20" v-if="$_isMobile()" style="position: absolute;top: 20px;left: 20px;">
            <el-button size="large" type="primary" @click="drawer=true" :icon="Menu" plain circle
                       :style="{marginLeft:drawer?'260px':'0'}"
            ></el-button>
        </el-affix>
        <el-main style="padding: 0 0 30px;" :class="{'pc-aside':!$_isMobile()}">
            <div
                    class="content-box"
                    :style="{overflow:(top)?'auto':'hidden'}">
                <about-me/>
                <self-introduction/>
                <experience/>
                <awards/>
                <scientific/>
                <my-photos/>
                <stack/>
                <contact-me></contact-me>
            </div>
        </el-main>
        <el-drawer v-model="drawer"
                   :append-to-body="false"
                   :size="260"
                   direction="ltr"
        >
            <side/>
        </el-drawer>
    </el-container>
</template>

<style scoped>
.pc-aside {
    position: absolute;
    left: 300px;
    width: calc(100% - 300px);
}
</style>