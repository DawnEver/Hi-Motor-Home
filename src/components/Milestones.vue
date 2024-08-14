<template>
    <v-sheet elevation="0" color="transparent" class="mx-10 my-10">
        <h1 class="font-weight-black text-h3 pb-2" align="center">
            {{ $t("milestone") }}
        </h1>
        <v-timeline side="end">
            <v-timeline-item v-for="(marker, i) in markers" :key="i" :dot-color="marker.color" size="small">
                <template v-slot:opposite>
                    <div :class="`pt-1 headline font-weight-bold text-${marker.color}`" v-text="marker.marker"></div>
                </template>
                <v-card hover :href="marker.link" target="_blanke">
                    <v-card-title :class="`mt-n1 headline font-weight-bold text-${marker.color}`">
                        {{marker.title}}
                    </v-card-title>
                    <v-card-text v-if="marker.content !== ''">
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
const { locale } = useI18n()
const markers = computed(() => {
    const lang = locale.value;
    if (lang === "zhHans") {
        return [
            {
                color: 'cyan',
                marker: '2022年3月18日',
                title: '梦开始的地方',
                content: '师生一拍即合，成立 5 人创始团队。',
                link: '',
            },
            {
                color: 'orange',
                marker: '2023年7月2日',
                title: '上线 Hi-Motor Designer 产品官网',
                content: '访问 https://designer.hi-motor.site',
                link: 'https://designer.hi-motor.site',
            },
            {
                color: 'amber',
                marker: '2023年7月23日',
                title: '上线 Hi-Motor Hub',
                content: '访问 https://hub.hi-motor.site',
                link: 'https://hub.hi-motor.site',
            },
            {
                color: 'green',
                marker: '2024年1月4日',
                title: '新的起点',
                content: '成立武汉伏特沃克科技有限公司',
                link: 'https://voltworks.cn',
            },
            {
                color: 'pink',
                marker: '2024年2月8日',
                title: '上线产品官网',
                content: '访问 https://voltworks.cn 或 https://hi-motor.site',
                link: 'https://voltworks.cn',
            },
            {
                color: 'red',
                marker: '2024年3月1日',
                title: 'Hi-Motor Designer 0.1.0 发布',
                content: '发布包含电机建模和有限元仿真等基本功能的 Hi-Motor Designer 0.1.0。',
                link: 'https://designer.hi-motor.site',
            },
        ]
    } else {
        return [
            {
                color: 'cyan',
                marker: 'March 18,2022',
                title: 'The begining',
                content: 'A 5-people founding team was formed.',
                link: '',
            },
            {
                color: 'orange',
                marker: 'July 2,2023',
                title: 'Release Hi-Motor Designer Product Site',
                content: 'Visit https://designer.hi-motor.site',
                link: 'https://designer.hi-motor.site',
            },
            {
                color: 'amber',
                marker: 'July 23,2023',
                title: 'Release Hi-Motor Hub',
                content: 'Visit https://hub.hi-motor.site',
                link: 'https://hub.hi-motor.site',

            },
            {
                color: 'green',
                marker: 'Jan 4,2024',
                title: 'Set up Wuhan Voltworks S&T Ltd.',
                content: 'Wuhan Voltworks S&T Ltd. was founded in HUST',
                link: 'https://voltworks.cn',
            },
            {
                color: 'pink',
                marker: 'Feb 8,2024',
                title: 'Release Official site',
                content: 'visit https://voltworks.cn or https://hi-motor.site',
                link: 'https://voltworks.cn',
            },
            {
                color: 'red',
                marker: 'March 1,2024',
                title: 'Release Hi-Motor Designer 0.1.0',
                content: 'Hi-Motor Designer 0.1.0 was released with basic functions including motor modeling and FEA simulation.',
                link: 'https://designer.hi-motor.site',
            },
        ]
    }

    });

</script>