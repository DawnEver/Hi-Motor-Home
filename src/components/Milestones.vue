<template>
    <v-sheet elevation="0" color="transparent" class="mx-10 my-10">
        <h1 class="font-weight-black text-h3 pb-2" align="center">
            {{ $t("milestone") }}
        </h1>
        <v-timeline side="end">
            <v-timeline-item v-for="(marker, i) in markers" :key="i" :dot-color="colors[i]" size="small">
                <template v-slot:opposite>
                    <div :class="`pt-1 headline font-weight-bold text-${colors[i]} text-h5`" v-text="marker.marker"></div>
                </template>
                <v-card hover :href="marker.link" target="_blanke">
                    <v-card-title :class="`mt-n1 headline font-weight-bold text-${colors[i]} text-h5`">
                        {{marker.title}}
                    </v-card-title>
                    <v-card-text v-if="marker.content !== ''" class="text-h6">
                        {{marker.content}}
                    </v-card-text>
                </v-card>
            </v-timeline-item>
        </v-timeline>
    </v-sheet>
</template>

<script setup lang="ts">
import { computed } from 'vue'
import { useI18n } from 'vue-i18n' // 多语言
const colors = ['red', 'pink', 'purple', 'deep-purple', 'indigo', 'blue', 'light-blue', 'cyan', 'teal', 'green', 'light-green', 'lime', 'yellow', 'amber', 'orange', 'deep-orange', 'brown', 'blue-grey', 'grey'];
const { locale } = useI18n();

const markers = computed(() => {
    const lang = locale.value;
    if (lang === "zhHans") {
        return [
            {
                marker: '2021年9月',
                title: '梦开始的地方',
                content: '几名来自华科电气2102班的学生和他们的教师班主任一拍即合。',
                link: '',
            },
            {
                marker: '2022年3月18日',
                title: '4 + 1 创始团队',
                content: '开始开发 Hi-Motor Designer Demo 版。',
                link: '',
            },
            {
                marker: '2023年7月19日',
                title: '上线 Hi-Motor Hub 电机选型平台',
                content: '访问 hub.hi-motor.site',
                link: 'https://hub.hi-motor.site',
            },
            {
                marker: '2024年1月4日',
                title: '新的起点',
                content: '成立武汉伏特沃克科技有限公司',
                link: 'https://voltworks.cn',
            },
            {
                marker: '2024年1月25日',
                title: '上线团队官网',
                content: '访问 voltworks.cn 或 hi-motor.site',
                link: 'https://voltworks.cn',
            },
            {
                marker: '2024年3月1日',
                title: 'Hi-Motor Designer 0.1.0 发布',
                content: '发布包含电机建模和有限元仿真等基本功能的 Hi-Motor Designer 0.1.0。',
                link: 'https://designer.hi-motor.site',
            },
            {
                marker: '2024年8月8日',
                title: '上线 Hi-Motor Designer 产品官网',
                content: '访问 designer.hi-motor.site',
                link: 'https://designer.hi-motor.site',
            },
            {
                marker: '2024年8月17日',
                title: '“象新力杯”大学生电力创新设计竞赛全国特等奖',
                content: '全场成绩第一！',
                link: 'https://mp.weixin.qq.com/s/GKNh5m0eaE8LiXhXewAHAg',
            },
            {
                marker: '2024年10月15日',
                title: '中国国际大学生创新大赛（2024）全国金奖',
                content: '金奖争夺赛小组第一，入围晋级排位赛！',
                link: 'https://news.hust.edu.cn/info/1002/53804.htm',
            },
        ]
    } else {
        return [
            {
                marker: 'September 2021',
                title: 'Where the Dream Began',
                content: 'Several students from Class 2102 of the School of Electrical and Electronic Engineering at HUST and their academic advisor hit it off.',
                link: '',
            },
            {
                marker: 'March 18, 2022',
                title: '4 + 1 Founding Team',
                content: 'Started developing the Hi-Motor Designer Demo version.',
                link: '',
            },
            {
                marker: 'July 19, 2023',
                title: 'Launch of Hi-Motor Hub Motor Selection Platform',
                content: 'Visit hub.hi-motor.site',
                link: 'https://hub.hi-motor.site',
            },
            {
                marker: 'January 4, 2024',
                title: 'A New Beginning',
                content: 'Established Wuhan Voltworks Technology Co., Ltd.',
                link: 'https://voltworks.cn',
            },
            {
                marker: 'January 25, 2024',
                title: 'Launch of Team Official Website',
                content: 'Visit voltworks.cn or hi-motor.site',
                link: 'https://voltworks.cn',
            },
            {
                marker: 'March 1, 2024',
                title: 'Hi-Motor Designer 0.1.0 Released',
                content: 'Released Hi-Motor Designer 0.1.0 with basic features such as motor modeling and finite element simulation.',
                link: 'https://designer.hi-motor.site',
            },
            {
                marker: 'August 8, 2024',
                title: 'Launch of Hi-Motor Designer Product Website',
                content: 'Visit designer.hi-motor.site',
                link: 'https://designer.hi-motor.site',
            },
            {
                marker: 'August 17, 2024',
                title: 'National Grand Prize in the "Xiangxinli Cup" College Student Electric Power Innovation Design Competition',
                content: 'Ranked first overall!',
                link: 'https://mp.weixin.qq.com/s/GKNh5m0eaE8LiXhXewAHAg',
            },
            {
                marker: 'October 15, 2024',
                title: 'National Gold Medal in the China International College Students Innovation Competition (2024)',
                content: 'Ranked first in the group stage of the gold medal competition and advanced to the ranking round!',
                link: 'https://news.hust.edu.cn/info/1002/53804.htm',
            },
        ]
    }

    });

</script>