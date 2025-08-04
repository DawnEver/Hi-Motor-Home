<template>
    <v-sheet class="mx-10 my-10">
        <h1 :class="`${titleClass} font-weight-black`" align="center">
            {{ $t("milestone") }}
        </h1>
        <v-infinite-scroll color="secondary" height="800px" @load="load">
            <template v-for="(milestone, i) in milestonesList" :key="i">
                <v-row class="ma-0">
                    <v-col cols="12" md="3" class="py-0 d-flex justify-center">
                        <div
                            :class="`pt-1 headline font-weight-bold text-${colors[i % colors.length]} ${itemTitleClass}`">
                            {{ milestone.marker }}
                        </div>
                    </v-col>
                    <v-col cols="12" md="9" class="py-0">
                        <v-card hover class="mb-6" :href="milestone.link" target="_blank">
                            <v-card-title
                                :class="`mt-n1 headline font-weight-bold text-${colors[i % colors.length]} ${cardTitleClass}`">
                                {{ milestone.title }}
                            </v-card-title>
                            <v-card-text v-if="milestone.content !== ''"
                                :class="`${cardTextClass} text-${colors[i % colors.length]}`">
                                {{ milestone.content }}
                            </v-card-text>
                        </v-card>
                    </v-col>
                </v-row>
            </template>
            <template #empty>
                <div :class="`${cardTextClass}`">{{ $t("moreMilestones") }}</div>
            </template>
        </v-infinite-scroll>
    </v-sheet>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue'
import { useI18n } from 'vue-i18n'
const { locale } = useI18n();
import useResponsiveFonts from '@/composables/useResponsiveFonts';
const { titleClass, itemTitleClass, cardTitleClass, cardTextClass, cardActionClass } = useResponsiveFonts();

const colors = ['red', 'pink', 'purple', 'deep-purple', 'indigo', 'blue', 'light-blue', 'cyan', 'teal', 'green', 'amber', 'orange', 'deep-orange', 'brown', 'blue-grey', 'grey'];

const milestones = computed(() => {
    const lang = locale.value;
    if (lang === "zhHans") {
        return [
            {
                marker: '2021年9月',
                title: '梦开始的地方',
                content: '几名来自华科电气2102班的学生和他们的教师班主任在华科相遇。',
                link: '',
            },
            {
                marker: '2022年3月17-18日',
                title: '一拍即合! 4 + 1 创始团队',
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
                title: '新的尝试',
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
                title: '“象新力杯”大学生电力创新设计竞赛',
                content: '“象新力杯”大学生电力创新设计竞赛全国特等奖，全场成绩第一！',
                link: 'https://mp.weixin.qq.com/s/GKNh5m0eaE8LiXhXewAHAg',
            },
            {
                marker: '2024年10月15日',
                title: '中国国际大学生创新大赛',
                content: '中国国际大学生创新大赛（2024）全国金奖，金奖争夺赛小组第一，入围晋级排位赛！',
                link: 'https://news.hust.edu.cn/info/1002/53804.htm',
            },
            {
                marker: '2024年11月10日',
                title: '全国大学生创新年会',
                content: '第十七届全国大学生创新年会获得“最佳创意项目”奖！',
                link: 'https://seee.hust.edu.cn/info/1124/18328.htm',
            },
            {
                marker: '2025年4月16日',
                title: '示范性学生创新团队',
                content: '入围华中科技大学年度示范性学生创新团队',
                link: 'https://news.hust.edu.cn/info/1004/55100.htm',
            },
            {
                marker: '2025年5月29日',
                title: '挑战杯省赛',
                content: '湖北省第十五届“挑战杯”大学生课外学术科技作品竞赛省赛一等奖',
                link: 'https://mp.weixin.qq.com/s/GsOteUSmY6153bSX30SNDA',
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
                marker: 'March 17-18, 2022',
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
                title: '“Xiangxinli Cup” National College Student Power Innovation Design Competition',
                content: 'Won the national grand prize in the “Xiangxinli Cup” National College Student Power Innovation Design Competition, ranked first overall!',
                link: 'https://mp.weixin.qq.com/s/GKNh5m0eaE8LiXhXewAHAg',
            },
            {
                marker: 'October 15, 2024',
                title: 'China International College Students’ Innovation Competition',
                content: 'Won the national gold award in the China International College Students’ Innovation Competition (2024), ranked first in the group stage of the gold medal competition and advanced to the ranking round!',
                link: 'https://news.hust.edu.cn/info/1002/53804.htm',
            },
            {
                marker: 'November 10, 2024',
                title: 'National College Student Innovation Annual Conference',
                content: 'Won the "Best Creative Project" award at the 17th National College Student Innovation Annual Conference!',
                link: 'https://seee.hust.edu.cn/info/1124/18328.htm',
            },
            {
                marker: 'April 16, 2025',
                title: 'Model Student Innovation Team',
                content: 'Selected as the Model Student Innovation Team of the Year at Huazhong University of Science and Technology',
                link: 'https://news.hust.edu.cn/info/1004/55100.htm',
            },
            {
                marker: 'May 29, 2025',
                title: 'First Prize in the Provincial Challenge Cup',
                content: 'First Prize in the 15th Hubei Province "Challenge Cup" College Student Academic Science and Technology Works Competition',
                link: 'https://mp.weixin.qq.com/s/GsOteUSmY6153bSX30SNDA',
            },
        ]
    }

});

const milestonesList = ref(milestones.value.slice(0, 6))

function load({ done }: { done: (status: string) => void }) {
    setTimeout(() => {
        const next = milestones.value.slice(milestonesList.value.length, milestonesList.value.length + 6)
        milestonesList.value.push(...next)
        if (milestonesList.value.length >= milestones.value.length) {
            done('empty')
        } else {
            done('ok')
        }
    }, 100)
}
import { watch } from 'vue'
watch(locale, () => {
    milestonesList.value = milestones.value
})

</script>