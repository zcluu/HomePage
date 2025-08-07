<script>
import {defineComponent} from 'vue'

export default defineComponent({
    name: "myPhotos"
})
</script>
<script setup>
import {LazyImg, Waterfall} from 'vue-waterfall-plugin-next'
import 'vue-waterfall-plugin-next/dist/style.css'
import BaseComponent from "@/components/baseComponent.vue";

let list = []
for (let i = 0; i < 20; i++) {
    list.push({src: '/static/photos/' + i + '.png'})
}
let breakpoints = {
    1200: { //当屏幕宽度小于等于1200
        rowPerView: 4,
    },
    800: { //当屏幕宽度小于等于800
        rowPerView: 3,
    },
    500: { //当屏幕宽度小于等于500
        rowPerView: 2,
    }
}
</script>

<template>
    <base-component
            id="photo"
            sub_title="PHOTO"
            main_title="MY PHOTOS"
            :is-white="true"
    >
        <template #mainBox>
            <Waterfall :list="list" :width="300">
                <template #item="{ item, url, index }">
                    <LazyImg :url="url"/>
                </template>
            </Waterfall>
        </template>
    </base-component>
</template>

<style scoped lang="less">

</style>