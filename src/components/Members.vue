<template>
  <v-sheet class="mx-auto my-10">
    <h1 :class="`${titleClass} font-weight-black`" align="center">
      {{ $t("member") }}
    </h1>
    <v-infinite-scroll color="secondary" height="800px" @load="load">
      <v-container>
        <v-row>
          <v-col v-for="(member, i) in membersList" :key="i" cols="12" sm="6" md="4" lg="3" xl="2">
            <v-card hover class="mb-6">
              <v-card-title :class="`headline font-weight-bold ${cardTitleClass}`">
                <a v-if="member.link" :href="member.link" target="_blank" style="text-decoration:none; color:inherit;">
                  {{ member.name }}
                  <v-icon size="x-small">mdi-open-in-new</v-icon>
                </a>
                <span v-else>{{ member.name }}</span>
              </v-card-title>
              <v-card-subtitle :class="`font-weight-bold ${itemTitleClass}`">
                {{ member.role }}
              </v-card-subtitle>
              <v-card-text :class="cardTextClass">
                {{ member.content }}
              </v-card-text>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
      <template #empty>
        <div :class="`${cardTextClass}`">{{ $t("moreMembers") }}</div>
      </template>
    </v-infinite-scroll>
  </v-sheet>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue'
import useResponsiveFonts from '@/composables/useResponsiveFonts';
const { titleClass, itemTitleClass, cardTitleClass, cardTextClass, cardActionClass } = useResponsiveFonts()

import { useI18n } from 'vue-i18n'
const { locale } = useI18n();

const members = computed(() => {
  const lang = locale.value;
  if (lang === "zhHans") {
    return [
      {
        name: '包铭阳',
        role: '联合创始人',
        content: '诺丁汉大学电气与电子工程学院25级博士(updated 2025.10)',
        link: 'https://www.baomingyang.site',
      },
      {
        name: '李俊昊',
        role: '联合创始人',
        content: '华中科技大学电气与电子工程学院25级硕士(updated 2025.10)',
      },
      {
        name: '冯思媛',
        role: '联合创始人',
        content: '华中科技大学电气与电子工程学院25级硕士(updated 2025.10)',
      },
      {
        name: '何廷科',
        role: '联合创始人',
        content: '华中科技大学电气与电子工程学院25级硕士(updated 2025.10)',
      },
      {
        name: '王亚玮',
        role: '联合创始人&指导老师',
        content: '华中科技大学电气学院副研究员(updated 2025.6)',
        link: 'http://faculty.hust.edu.cn/WANGYAWEI/zh_CN/index.htm',
      },
      {
        name: '丁秀好',
        role: '指导老师',
        content: '华中科技大学经济学院教授(updated 2025.6)',
        link: 'https://cm.hust.edu.cn/info/1750/24555.htm',
      },
      {
        name: '李大伟',
        role: '指导老师',
        content: '华中科技大学电气学院教授(updated 2025.6)',
        link: 'http://faculty.hust.edu.cn/lidawei/zh_CN/index.htm',
      },
      {
        name: '曲荣海',
        role: '指导老师',
        content: '华中科技大学电气学院教授(updated 2025.6)',
        link: 'http://faculty.hust.edu.cn/quronghai/zh_CN/index.htm',
      },
      {
        name: '卫平',
        role: '指导老师',
        content: '华中科技大学经济学院教授(updated 2025.6)',
        link: 'https://baike.baidu.com/item/卫平/4124575',
      },
      {
        name: '于德水',
        role: '团队成员',
        content: '华中科技大学管理学院21级本科生(updated 2025.6)',
      },
      {
        name: '卢舒愉',
        role: '团队成员',
        content: '新加坡国立大学计算机学院25级博士(updated 2025.10)',
        link: 'https://lushuyu.site',
      },
      {
        name: '杨堪然',
        role: '团队成员',
        content: '华中科技大学管理学院25级硕士(updated 2025.10)',
      },
      {
        name: '毛晨燊',
        role: '团队成员',
        content: '清华大学电气学院25级硕士(updated 2025.6)',
      },
      {
        name: '涂宜帅',
        role: '团队成员',
        content: '华中科技大学电气与电子工程学院25级硕士(updated 2025.10)',
      },
      {
        name: '刘宇杰',
        role: '团队成员',
        content: '华中科技大学电气与电子工程学院22级本科生(updated 2025.10)',
      },
      {
        name: '唐宇桓',
        role: '团队成员',
        content: '华中科技大学电气与电子工程学院22级本科生(updated 2025.10)',
      },
      {
        name: '朱开翼',
        role: '团队成员',
        content: '华中科技大学电气与电子工程学院22级本科生(updated 2025.10)',
      },
      {
        name: '陈功',
        role: '团队成员',
        content: '华中科技大学电气与电子工程学院23级本科生(updated 2025.10)',
      },
      {
        name: '刘敖君',
        role: '团队成员',
        content: '华中科技大学电气与电子工程学院23级本科生(updated 2025.10)',
      },
      {
        name: '周豪克',
        role: '团队成员',
        content: '华中科技大学电气与电子工程学院23级本科生(updated 2025.10)',
      },
      {
        name: '张天',
        role: '团队成员',
        content: '华中科技大学法学院25级硕士(updated 2025.10)',
      },
      {
        name: '罗钰雯',
        role: '团队成员',
        content: '华中科技大学新闻学院22级本科生(updated 2025.10)',
      },
      {
        name: '刘佳仪',
        role: '团队成员',
        content: '华中科技大学管理学院21级本科生(updated 2025.10)',
      },
      {
        name: '董维宁',
        role: '团队成员',
        content: '华中科技大学电气与电子工程学院22级本科生(updated 2025.10)',
      },
      {
        name: '吕钰仪',
        role: '团队成员',
        content: '华中科技大学管理学院23级本科生(updated 2025.10)',
      },
      {
        name: '陈继东',
        role: '团队成员',
        content: '华中科技大学电气与电子工程学院23级本科生(updated 2025.10)',
      },
      {
        name: '吴文博',
        role: '团队成员',
        content: '华中科技大学电气与电子工程学院24级本科生(updated 2025.10)',
      },
      {
        name: '熊翊辰',
        role: '团队成员',
        content: '华中科技大学电气与电子工程学院23级本科生(updated 2025.10)',
      },
      {
        name: '郝铭源',
        role: '团队成员',
        content: '华中科技大学电气与电子工程学院23级本科生(updated 2025.10)',
      },
      {
        name: '黄建平',
        role: '团队成员',
        content: '华中科技大学电气与电子工程学院23级本科生(updated 2025.10)',
      },
      {
        name: '肖雅逸',
        role: '团队成员',
        content: '华中科技大学电气与电子工程学院23级本科生(updated 2025.10)',
      },
      {
        name: '黄嘉豪',
        role: '团队成员',
        content: '华中科技大学电气与电子工程学院24级本科生(updated 2025.10)',
      },
      {
        name: '张亦璐',
        role: '团队成员',
        content: '华中科技大学电气与电子工程学院23级本科生(updated 2025.10)',
      },
      {
        name: '王柯淳',
        role: '团队成员',
        content: '华中科技大学电气与电子工程学院23级本科生(updated 2025.10)',
      },
      {
        name: '马慧',
        role: '团队成员',
        content: '华中科技大学管理学院23级本科生(updated 2025.10)',
      },
      {
        name: '付虹玥',
        role: '团队成员',
        content: '华中科技大学管理学院24级本科生(updated 2025.10)',
      },
      {
        name: '梁鸿元',
        role: '荣誉成员',
        content: '华中科技大学电气与电子工程学院24级博士(updated 2025.10)',
      },
      {
        name: '程宇航',
        role: '荣誉成员',
        content: '华中科技大学电气与电子工程学院21级硕士(updated 2024.6)',
      },
      {
        name: '李宣',
        role: '荣誉成员',
        content: '华中科技大学电气与电子工程学院21级硕士(updated 2024.6)',
      },
      {
        name: '陈远健',
        role: '荣誉成员',
        content: '华中科技大学电气与电子工程学院22级硕士(updated 2025.6)',
      },
      {
        name: '郑晔明',
        role: '荣誉成员',
        content: '华中科技大学电气与电子工程学院22级博士(updated 2025.6)',
      },
      {
        name: '陈武韬',
        role: '荣誉成员',
        content: '华中科技大学电气与电子工程学院23级硕士(updated 2025.6)',
      },
      {
        name: '唐悦',
        role: '荣誉成员',
        content: '华中科技大学电气与电子工程学院23级硕士(updated 2025.6)',
      },
      {
        name: '贺银杰',
        role: '荣誉成员',
        content: '华中科技大学电气与电子工程学院24级硕士(updated 2025.6)',
      },
      {
        name: '张晨',
        role: '荣誉成员',
        content: '华中科技大学电气与电子工程学院24级博士(updated 2025.6)',
      },
      {
        name: '马冲',
        role: '荣誉成员',
        content: '华中科技大学电气与电子工程学院25级硕士(updated 2025.10)',
      },
      {
        name: '李文扬',
        role: '荣誉成员',
        content: '华中科技大学电气与电子工程学院25级博士(updated 2025.10)',
      },
      {
        name: '徐珉轩',
        role: '荣誉成员',
        content: '华中科技大学电气与电子工程学院25级硕士(updated 2025.10)',
      },
      {
        name: '周扶林',
        role: '荣誉成员',
        content: '华中科技大学电气与电子工程学院25级博士(updated 2025.10)',
      },
      {
        name: '王金玉',
        role: '荣誉成员',
        content: '华中科技大学电气与电子工程学院25级硕士(updated 2025.10)',
      }
    ]
  } else {
    return [
      {
        name: 'Bao Mingyang',
        role: 'Co-founder',
        content: 'PhD student at the University of Nottingham, School of Electrical and Electronic Engineering (updated 2025.10)',
        link: 'https://www.baomingyang.site',
      },
      {
        name: 'Li Junhao',
        role: 'Co-founder',
        content: 'Master student at Huazhong University of Science and Technology, School of Electrical and Electronic Engineering (updated 2025.10)',
      },
      {
        name: 'Feng Siyuan',
        role: 'Co-founder',
        content: 'Master student at Huazhong University of Science and Technology, School of Electrical and Electronic Engineering (updated 2025.10)',
      },
      {
        name: 'He Tingke',
        role: 'Co-founder',
        content: 'Master student at Huazhong University of Science and Technology, School of Electrical and Electronic Engineering (updated 2025.10)',
      },
      {
        name: 'Wang Yawei',
        role: 'Co-founder & Advisor',
        content: 'Associate Researcher at Huazhong University of Science and Technology, School of Electrical Engineering (updated 2025.6)',
        link: 'http://faculty.hust.edu.cn/WANGYAWEI/en/index.htm',
      },
      {
        name: 'Ding Xiuhai',
        role: 'Advisor',
        content: 'Professor at Huazhong University of Science and Technology, School of Economics (updated 2025.6)',
        link: 'https://cm.hust.edu.cn/info/1750/24555.htm',
      },
      {
        name: 'Li Dawei',
        role: 'Advisor',
        content: 'Professor at Huazhong University of Science and Technology, School of Electrical Engineering (updated 2025.6)',
        link: 'http://faculty.hust.edu.cn/lidawei/en/index.htm',
      },
      {
        name: 'Qu Ronghai',
        role: 'Advisor',
        content: 'Professor at Huazhong University of Science and Technology, School of Electrical Engineering (updated 2025.6)',
        link: 'http://faculty.hust.edu.cn/quronghai/en/index.htm',
      },
      {
        name: 'Wei Ping',
        role: 'Advisor',
        content: 'Professor at Huazhong University of Science and Technology, School of Economics (updated 2025.6)',
        link: 'https://baike.baidu.com/item/卫平/4124575',
      },
      {
        name: 'Yu Deshui',
        role: 'Team Member',
        content: 'Undergraduate student at Huazhong University of Science and Technology, School of Management (updated 2025.6)',
      },
      {
        name: 'Lu Shuyu',
        role: 'Team Member',
        content: 'PhD student at National University of Singapore, School of Computer Science (updated 2025.10)',
        link: 'https://lushuyu.site',
      },
      {
        name: 'Yang Kanran',
        role: 'Team Member',
        content: 'Master student at Huazhong University of Science and Technology, School of Management (updated 2025.10)',
      },
      {
        name: 'Mao Chenshen',
        role: 'Team Member',
        content: 'Master student at Tsinghua University, School of Electrical Engineering (updated 2025.6)',
      },
      {
        name: 'Tu Yishui',
        role: 'Team Member',
        content: 'Master student at Huazhong University of Science and Technology, School of Electrical and Electronic Engineering (updated 2025.10)',
      },
      {
        name: 'Liu Yujie',
        role: 'Team Member',
        content: 'Undergraduate student at Huazhong University of Science and Technology, School of Electrical and Electronic Engineering (updated 2025.10)',
      },
      {
        name: 'Tang Yuhuan',
        role: 'Team Member',
        content: 'Undergraduate student at Huazhong University of Science and Technology, School of Electrical and Electronic Engineering (updated 2025.10)',
      },
      {
        name: 'Zhu Kaiyi',
        role: 'Team Member',
        content: 'Undergraduate student at Huazhong University of Science and Technology, School of Electrical and Electronic Engineering (updated 2025.10)',
      },
      {
        name: 'Chen Gong',
        role: 'Team Member',
        content: 'Undergraduate student at Huazhong University of Science and Technology, School of Electrical and Electronic Engineering (updated 2025.10)',
      },
      {
        name: 'Liu Aojun',
        role: 'Team Member',
        content: 'Undergraduate student at Huazhong University of Science and Technology, School of Electrical and Electronic Engineering (updated 2025.10)',
      },
      {
        name: 'Zhou Haoke',
        role: 'Team Member',
        content: 'Undergraduate student at Huazhong University of Science and Technology, School of Electrical and Electronic Engineering (updated 2025.10)',
      },
      {
        name: 'Zhang Tian',
        role: 'Team Member',
        content: 'Master student at Huazhong University of Science and Technology, School of Law (updated 2025.10)',
      },
      {
        name: 'Luo Yuwen',
        role: 'Team Member',
        content: 'Undergraduate student at Huazhong University of Science and Technology, School of Journalism (updated 2025.10)',
      },
      {
        name: 'Liu Jiayi',
        role: 'Team Member',
        content: 'Undergraduate student at Huazhong University of Science and Technology, School of Management (updated 2025.10)',
      },
      {
        name: 'Dong Weining',
        role: 'Team Member',
        content: 'Undergraduate student at Huazhong University of Science and Technology, School of Electrical and Electronic Engineering (updated 2025.10)',
      },
      {
        name: 'Lv Yuyi',
        role: 'Team Member',
        content: 'Undergraduate student at Huazhong University of Science and Technology, School of Management (updated 2025.10)',
      },
      {
        name: 'Chen Jidong',
        role: 'Team Member',
        content: 'Undergraduate student at Huazhong University of Science and Technology, School of Electrical and Electronic Engineering (updated 2025.10)',
      },
      {
        name: 'Wu Wenbo',
        role: 'Team Member',
        content: 'Undergraduate student at Huazhong University of Science and Technology, School of Electrical and Electronic Engineering (updated 2025.10)',
      },
      {
        name: 'Xiong Yichen',
        role: 'Team Member',
        content: 'Undergraduate student at Huazhong University of Science and Technology, School of Electrical and Electronic Engineering (updated 2025.10)',
      },
      {
        name: 'Hao Mingyuan',
        role: 'Team Member',
        content: 'Undergraduate student at Huazhong University of Science and Technology, School of Electrical and Electronic Engineering (updated 2025.10)',
      },
      {
        name: 'Huang Jianping',
        role: 'Team Member',
        content: 'Undergraduate student at Huazhong University of Science and Technology, School of Electrical and Electronic Engineering (updated 2025.10)',
      },
      {
        name: 'Xiao Yayi',
        role: 'Team Member',
        content: 'Undergraduate student at Huazhong University of Science and Technology, School of Electrical and Electronic Engineering (updated 2025.10)',
      },
      {
        name: 'Huang Jiahao',
        role: 'Team Member',
        content: 'Undergraduate student at Huazhong University of Science and Technology, School of Electrical and Electronic Engineering (updated 2025.10)',
      },
      {
        name: 'Zhang Yilu',
        role: 'Team Member',
        content: 'Undergraduate student at Huazhong University of Science and Technology, School of Electrical and Electronic Engineering (updated 2025.10)',
      },
      {
        name: 'Wang Kechun',
        role: 'Team Member',
        content: 'Undergraduate student at Huazhong University of Science and Technology, School of Electrical and Electronic Engineering (updated 2025.10)',
      },
      {
        name: 'Ma Hui',
        role: 'Team Member',
        content: 'Undergraduate student at Huazhong University of Science and Technology, School of Management (updated 2025.10)',
      },
      {
        name: 'Fu Hongyue',
        role: 'Team Member',
        content: 'Undergraduate student at Huazhong University of Science and Technology, School of Management (updated 2025.10)',
      },
      {
        name: 'Liang Hongyuan',
        role: 'Honorary Member',
        content: 'PhD student at Huazhong University of Science and Technology, School of Electrical and Electronic Engineering (updated 2025.10)',
      },
      {
        name: 'Cheng Yuhang',
        role: 'Honorary Member',
        content: 'Master student at Huazhong University of Science and Technology, School of Electrical and Electronic Engineering (updated 2024.6)',
      },
      {
        name: 'Li Xuan',
        role: 'Honorary Member',
        content: 'Master student at Huazhong University of Science and Technology, School of Electrical and Electronic Engineering (updated 2024.6)',
      },
      {
        name: 'Chen Yuanjian',
        role: 'Honorary Member',
        content: 'Master student at Huazhong University of Science and Technology, School of Electrical and Electronic Engineering (updated 2025.6)',
      },
      {
        name: 'Zheng Yeming',
        role: 'Honorary Member',
        content: 'PhD student at Huazhong University of Science and Technology, School of Electrical and Electronic Engineering (updated 2025.6)',
      },
      {
        name: 'Chen Wutao',
        role: 'Honorary Member',
        content: 'Master student at Huazhong University of Science and Technology, School of Electrical and Electronic Engineering (updated 2025.6)',
      },
      {
        name: 'Tang Yue',
        role: 'Honorary Member',
        content: 'Master student at Huazhong University of Science and Technology, School of Electrical and Electronic Engineering (updated 2025.6)',
      },
      {
        name: 'He Yinjie',
        role: 'Honorary Member',
        content: 'Master student at Huazhong University of Science and Technology, School of Electrical and Electronic Engineering (updated 2025.6)',
      },
      {
        name: 'Zhang Chen',
        role: 'Honorary Member',
        content: 'PhD student at Huazhong University of Science and Technology, School of Electrical and Electronic Engineering (updated 2025.6)',
      },
      {
        name: 'Ma Chong',
        role: 'Honorary Member',
        content: 'Master student at Huazhong University of Science and Technology, School of Electrical and Electronic Engineering (updated 2025.10)',
      },
      {
        name: 'Li Wenyang',
        role: 'Honorary Member',
        content: 'PhD student at Huazhong University of Science and Technology, School of Electrical and Electronic Engineering (updated 2025.10)',
      },
      {
        name: 'Xu Minxuan',
        role: 'Honorary Member',
        content: 'Master student at Huazhong University of Science and Technology, School of Electrical and Electronic Engineering (updated 2025.10)',
      },
      {
        name: 'Zhou Fulin',
        role: 'Honorary Member',
        content: 'PhD student at Huazhong University of Science and Technology, School of Electrical and Electronic Engineering (updated 2025.10)',
      },
      {
        name: 'Wang Jinyu',
        role: 'Honorary Member',
        content: 'Master student at Huazhong University of Science and Technology, School of Electrical and Electronic Engineering (updated 2025.10)',
      }
    ]
  }
});
const membersList = ref(members.value.slice(0, 12))

function load({ done }: { done: (status: string) => void }) {
  setTimeout(() => {
    // 每次加载成员，直到全部加载完
    const next = members.value.slice(membersList.value.length, membersList.value.length + 12)
    membersList.value.push(...next)
    if (membersList.value.length >= members.value.length) {
      done('empty')
    } else {
      done('ok')
    }
  }, 100)
}

// 监听语言切换，重置membersList
import { watch } from 'vue'
watch(locale, () => {
  membersList.value = members.value
})
</script>
