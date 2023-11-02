<template>
    <base-component
            sub_title="EXPERIENCE"
            main_title="MY EXPERIENCE"
            id="experience"
    >
        <template #mainBox>
            <div class="time-box">
                <el-scrollbar
                        max-height="600px"
                >
                    <el-timeline>
                        <el-timeline-item v-for="item in items" :key="item" :hollow="true" type="primary"
                                          :timestamp="item.time"
                                          placement="top"
                        >
                            <el-card>
                                <template #header>
                                    <div class="card-header">
                                        <span>{{ item.title }}</span>
                                    </div>
                                </template>
                                {{ item.content }}
                            </el-card>
                        </el-timeline-item>
                    </el-timeline>
                </el-scrollbar>
            </div>
        </template>
    </base-component>
</template>

<script>
export default {
    name: "Experience"
}
</script>
<script setup>
import BaseComponent from "./baseComponent.vue";

const items = [
    {
        time: '2019/09',
        title: '山东财经大学',
        content: '初入大学，感谢SDUFE对自己三年来的培养，校训“克明俊德、格物致知”时刻警醒着自己不断奋斗。很荣幸有机会在山财度过难忘的本科，期待“小破财”更好的未来！'
    },
    {
        time: '2019/10',
        title: '成为ACMer是成功的根源',
        content: '老生常谈的话题，ACM是计科人首选。很庆幸在入学时选择成为ACMer并为之奋斗三年之久。回首望，荣誉均与ACM有关，八年算法终将落幕，期待新的道路有所成就。'
    },
    {
        time: '2020/03',
        title: '疫情居家苦不堪言',
        content: '没体验过大一的愉悦，但体验到Coder的乐趣，难忘高强度工作12*7的自己，感谢当年奋斗的自己，逐渐相信没有什么是不可能的。探索自己的步伐，坚持挖掘新技术。'
    },
    {
        time: '2020/10~2020/11',
        title: '戴口罩、测核酸、外出比赛',
        content: '返校后比赛密集期，有遗憾、有快乐，尝试了个人赛、体验过团队赛，大学规划不再迷茫，坚信算法道路，面对编程不再迷惘。'
    },
    {
        time: '2021/05~2021/06',
        title: '长期休战，再次出战',
        content: '弥补前年遗憾，蓝桥挺进国赛，天梯赛夺得银奖。这是转型的开始，不再只是基础算法，更是各项技术、本领逐渐成熟的开始，点滴完善自身缺陷。'
    },
    {
        time: '2021/11~2022/04',
        title: '科研初探索，小白勇往直前',
        content: '新兴技术不断涌现，开始思考未来发展方向。感谢在迷茫时遇见，受人指点逐渐尝试机器视觉，跟随长江学者实验室展开课题，探索无限可能，相信自己潜力无穷，不断突破自我。'
    },
    {
        time: '2022/06~2022/08',
        title: '开始相信，一切都是最好的安排',
        content: '事情总不是一帆风顺，经历过挫折才可见得彩虹，感谢遇见良师，让生活看到一丝希望，感谢曾经奋斗过的自己，亦是点滴凝聚成河流，奔流向远方。'
    },
    {
        time: '2022/09.28',
        title: '何其有幸，进入国内Top5高校',
        content: '挫折后的彩虹格外亮眼，默默耕耘了三年之久，凭借扎实的基础成功进入不曾在梦中出现的学府继续攻读研究生，感恩这一路遇到的所有人，对我而言这是一个奇迹。'
    },
    {
        time: '2022/10',
        title: '小白蜕变，进入Top实验室',
        content: '生活在这一刻发生了巨大变化，自己不再独自奋斗，看到了与周围人的差距，突破Top5已是奇迹，相信这一切都不是问题，砥砺前行，奋勇直追。'
    },
    {
        time: '2023/03',
        title: '回归学校，还是那个味道',
        content: '离校半年之久，回校时拜见了恩师，和朋友一起叙旧，畅谈人生理想，看到考研的泪与笑，祝福同学一切顺利。'
    },
    {
        time: '2023/05',
        title: '毕业答辩，大学生活倒计时了',
        content: '起个大早一起去合照，一切都好快，这是班级最后一次集体活动，答辩后各奔东西，不知再见是何时，期待再见时都能实现自己的理想。'
    },
    {
        time: '2023/10',
        title: '硕士生活步入正轨，科研压力跌踵而至',
        content: '热爱自己的热爱，做喜欢的事，为了梦想砥砺前行，科研压力跌踵而至，不经意的改进有很好的效果，快乐居然如此简单。'
    },
]
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

  .maintitle {
    font-size: 2rem;
    letter-spacing: .2rem;
  }
}

.time-box {
  margin-top: 2rem;
}
</style>