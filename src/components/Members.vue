<template>
  <v-sheet class="mx-auto my-10">
    <h1 :class="`${titleClass} font-weight-black`" align="center">
      {{ $t("member") }}
    </h1>
    <v-infinite-scroll
      color="secondary"
      height="800px"
      @load="load"
    >
      <v-container>
        <v-row>
            <v-col
            v-for="(member, i) in membersList"
            :key="i"
            cols="12"
            sm="6"
            md="4"
            lg="3"
            xl="2"
            >
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
const {titleClass, itemTitleClass, cardTitleClass, cardTextClass, cardActionClass} = useResponsiveFonts()

import { useI18n } from 'vue-i18n'
const { locale } = useI18n();

const members = computed(() => {
  const lang = locale.value;
  if (lang === "zhHans") {
    return [
      {
        name: '包铭阳',
        role: '联合创始人',
        content: '诺丁汉大学电气与电子工程学院博士(2025.10)',
        link: 'https://www.baomingyang.site',
      },
      {
        name: '李俊昊',
        role: '联合创始人',
        content: '华中科技大学电气与电子工程学院硕士(2025.10)',
      },
      {
        name: '冯思媛',
        role: '联合创始人',
        content: '华中科技大学电气与电子工程学院硕士(2025.10)',
      },
      {
        name: '何廷科',
        role: '联合创始人',
        content: '华中科技大学电气与电子工程学院硕士(2025.10)',
      },
      {
        name: '王亚玮',
        role: '联合创始人&指导老师',
        content: '华中科技大学电气学院副研究员(2025.6)',
        link: 'http://faculty.hust.edu.cn/WANGYAWEI/zh_CN/index.htm',
      },
      {
        name: '丁秀好',
        role: '指导老师',
        content: '华中科技大学经济学院教授(2025.6)',
        link: 'https://cm.hust.edu.cn/info/1750/24555.htm',
      },
      {
        name: '李大伟',
        role: '指导老师',
        content: '华中科技大学电气学院教授(2025.6)',
        link: 'http://faculty.hust.edu.cn/lidawei/zh_CN/index.htm',
      },
      {
        name: '曲荣海',
        role: '指导老师',
        content: '华中科技大学电气学院教授(2025.6)',
        link: 'http://faculty.hust.edu.cn/quronghai/zh_CN/index.htm',
      },
      {
        name: '卫平',
        role: '指导老师',
        content: '华中科技大学经济学院教授(2025.6)',
        link: 'https://baike.baidu.com/item/卫平/4124575',
      },
      {
        name: '于德水',
        role: '团队成员',
        content: '华中科技大学管理学院本科生(2025.6)',
      },
      {
        name: '卢舒愉',
        role: '团队成员',
        content: '南洋理工大学计算机学院博士(2025.10)',
        link: 'https://lushuyu.site',
      },
      {
        name: '杨堪然',
        role: '团队成员',
        content: '华中科技大学管理学院硕士(2025.10)',
      },
      {
        name: '毛晨燊',
        role: '团队成员',
        content: '华中科技大学电气学院本科生(2025.6)',
      },
      {
        name: '涂宜帅',
        role: '团队成员',
        content: '华中科技大学电气与电子工程学院硕士(2025.10)',
      },
      {
        name: '刘宇杰',
        role: '团队成员',
        content: '华中科技大学电气与电子工程学院本科生(2025.10)',
      },
      {
        name: '唐宇桓',
        role: '团队成员',
        content: '华中科技大学电气与电子工程学院本科生(2025.10)',
      },
      {
        name: '朱开翼',
        role: '团队成员',
        content: '华中科技大学电气与电子工程学院本科生(2025.10)',
      },
      {
        name: '陈功',
        role: '团队成员',
        content: '华中科技大学电气与电子工程学院本科生(2025.10)',
      },
      {
        name: '刘敖君',
        role: '团队成员',
        content: '华中科技大学电气与电子工程学院本科生(2025.10)',
      },
      {
        name: '周豪克',
        role: '团队成员',
        content: '华中科技大学电气与电子工程学院本科生(2025.10)',
      },
      {
        name: '董维宁',
        role: '团队成员',
        content: '华中科技大学电气与电子工程学院本科生(2025.10)',
      },
      {
        name: '吕钰仪',
        role: '团队成员',
        content: '华中科技大学管理学院本科生(2025.10)',
      },
      {
        name: '张天',
        role: '团队成员',
        content: '华中科技大学法学院硕士(2025.10)',
      },
      {
        name: '罗钰雯',
        role: '团队成员',
        content: '华中科技大学新闻学院本科生(2025.10)',
      },
      {
        name: '刘佳仪',
        role: '团队成员',
        content: '华中科技大学管理学院本科生(2025.10)',
      },
      {
        name: '陈继东',
        role: '团队成员',
        content: '华中科技大学电气与电子工程学院本科生(2025.10)',
      },
      {
        name: '吴文博',
        role: '团队成员',
        content: '华中科技大学电气与电子工程学院本科生(2025.10)',
      },
      {
        name: '熊翊辰',
        role: '团队成员',
        content: '华中科技大学电气与电子工程学院本科生(2025.10)',
      },
      {
        name: '郝铭源',
        role: '团队成员',
        content: '华中科技大学电气与电子工程学院本科生(2025.10)',
      },
      {
        name: '黄建平',
        role: '团队成员',
        content: '华中科技大学电气与电子工程学院本科生(2025.10)',
      },
      {
        name: '肖雅逸',
        role: '团队成员',
        content: '华中科技大学电气与电子工程学院本科生(2025.10)',
      },
      {
        name: '黄嘉豪',
        role: '团队成员',
        content: '华中科技大学电气与电子工程学院本科生(2025.10)',
      },
      {
        name: '张亦璐',
        role: '团队成员',
        content: '华中科技大学电气与电子工程学院本科生(2025.10)',
      },
      {
        name: '王柯淳',
        role: '团队成员',
        content: '华中科技大学电气与电子工程学院本科生(2025.10)',
      },
      {
        name: '梁鸿元',
        role: '荣誉成员',
        content: '华中科技大学电气与电子工程学院博士(2025.10)',
      },
      {
        name: '程宇航',
        role: '荣誉成员',
        content: '华中科技大学电气与电子工程学院硕士(2024.6)',
      },
      {
        name: '李宣',
        role: '荣誉成员',
        content: '华中科技大学电气与电子工程学院硕士(2024.6)',
      },
      {
        name: '陈远健',
        role: '荣誉成员',
        content: '华中科技大学电气与电子工程学院硕士(2025.6)',
      },
      {
        name: '郑晔明',
        role: '荣誉成员',
        content: '华中科技大学电气与电子工程学院博士(2025.6)',
      },
      {
        name: '陈武韬',
        role: '荣誉成员',
        content: '华中科技大学电气与电子工程学院硕士(2025.6)',
      },
      {
        name: '唐悦',
        role: '荣誉成员',
        content: '华中科技大学电气与电子工程学院硕士(2025.6)',
      },
      {
        name: '贺银杰',
        role: '荣誉成员',
        content: '华中科技大学电气与电子工程学院硕士(2025.6)',
      },
      {
        name: '张晨',
        role: '荣誉成员',
        content: '华中科技大学电气与电子工程学院博士(2025.6)',
      },
      {
        name: '马冲',
        role: '荣誉成员',
        content: '华中科技大学电气与电子工程学院硕士(2025.10)',
      },
      {
        name: '李文扬',
        role: '荣誉成员',
        content: '华中科技大学电气与电子工程学院硕士(2025.10)',
      },
      {
        name: '徐珉轩',
        role: '荣誉成员',
        content: '华中科技大学电气与电子工程学院硕士(2025.10)',
      },
      {
        name: '周扶林',
        role: '荣誉成员',
        content: '华中科技大学电气与电子工程学院博士(2025.10)',
      }
    ]
  } else {
    return [
      {
      name: 'Mingyang Bao',
      role: 'Cofounder',
      content: 'University of Nottingham, SEE PhD(2025.10)',
      link: 'https://www.baomingyang.site',
      },
      {
      name: 'Junhao Li',
      role: 'Cofounder',
      content: 'Huazhong Univ. of Sci. & Tech., SEE M.E(2025.10)',
      },
      {
      name: 'Siyuan Feng',
      role: 'Cofounder',
      content: 'Huazhong Univ. of Sci. & Tech., SEE M.E(2025.10)',
      },
      {
      name: 'Tingke He',
      role: 'Cofounder',
      content: 'Huazhong Univ. of Sci. & Tech., SEE M.E(2025.10)',
      },
      {
      name: 'Yawei Wang',
      role: 'Cofounder&Adviser',
      content: 'Huazhong Univ. of Sci. & Tech., SEE Associate Professor(2025.6)',
      link: 'http://faculty.hust.edu.cn/WANGYAWEI/en/index.htm',
      },
      {
      name: 'Xiuhao Ding',
      role: 'Adviser',
      content: 'Huazhong Univ. of Sci. & Tech., SME Professor(2025.6)',
      link: 'https://cm.hust.edu.cn/info/1750/24555.htm',
      },
      {
      name: 'Dawei Li',
      role: 'Adviser',
      content: 'Huazhong Univ. of Sci. & Tech., SEE Professor(2025.6)',
      link: 'http://faculty.hust.edu.cn/lidawei/en/index.htm',
      },
      {
      name: 'Ronghai Qu',
      role: 'Adviser',
      content: 'Huazhong Univ. of Sci. & Tech., SEE Professor(2025.6)',
      link: 'http://faculty.hust.edu.cn/quronghai/en/index.htm',
      },
      {
      name: 'Ping Wei',
      role: 'Adviser',
      content: 'Huazhong Univ. of Sci. & Tech., SME Professor(2025.6)',
      link: 'https://baike.baidu.com/item/卫平/4124575',
      },
      {
      name: 'Deshui Yu',
      role: 'Member',
      content: 'Huazhong Univ. of Sci. & Tech., SME B.B.A(2025.6)',
      },
      {
      name: 'Shuyu Lu',
      role: 'Member',
      content: 'Nanyang University of Technology, CS PhD(2025.10)',
      link: 'https://lushuyu.site',
      },
      {
      name: 'Kanran Yang',
      role: 'Member',
      content: 'Huazhong Univ. of Sci. & Tech., SME M.B.A(2025.10)',
      },
      {
      name: 'Chenshen Mao',
      role: 'Member',
      content: 'Huazhong Univ. of Sci. & Tech., SEE B.E(2025.6)',
      },
      {
      name: 'Yishuai Tu',
      role: 'Member',
      content: 'Huazhong Univ. of Sci. & Tech., SEE M.E(2025.10)',
      },
      {
      name: 'Yujie Liu',
      role: 'Member',
      content: 'Huazhong Univ. of Sci. & Tech., SEE B.E(2025.10)',
      },
      {
      name: 'Yuhuan Tang',
      role: 'Member',
      content: 'Huazhong Univ. of Sci. & Tech., SEE B.E(2025.10)',
      },
      {
      name: 'Kaiyi Zhu',
      role: 'Member',
      content: 'Huazhong Univ. of Sci. & Tech., SEE B.E(2025.10)',
      },
      {
      name: 'Gong Chen',
      role: 'Member',
      content: 'Huazhong Univ. of Sci. & Tech., SEE B.E(2025.10)',
      },
      {
      name: 'Aojun Liu',
      role: 'Member',
      content: 'Huazhong Univ. of Sci. & Tech., SEE B.E(2025.10)',
      },
      {
      name: 'Haoke Zhou',
      role: 'Member',
      content: 'Huazhong Univ. of Sci. & Tech., SEE B.E(2025.10)',
      },
      {
      name: 'Weining Dong',
      role: 'Member',
      content: 'Huazhong Univ. of Sci. & Tech., SEE B.E(2025.10)',
      },
      {
      name: 'Yuyi Lü',
      role: 'Member',
      content: 'Huazhong Univ. of Sci. & Tech., SME B.B.A(2025.10)',
      },
      {
      name: 'Tian Zhang',
      role: 'Member',
      content: 'Huazhong Univ. of Sci. & Tech., S.Law B.Law(2025.6)',
      },
      {
      name: 'Yuwen Luo',
      role: 'Member',
      content: 'Huazhong Univ. of Sci. & Tech., S.Journal B.A(2025.10)',
      },
      {
      name: 'Jiayi Liu',
      role: 'Member',
      content: 'Huazhong Univ. of Sci. & Tech., SME B.Com(2025.10)',
      },
      {
      name: 'Jidong Chen',
      role: 'Member',
      content: 'Huazhong Univ. of Sci. & Tech., SEE B.E(2025.10)',
      },
      {
      name: 'Wenbo Wu',
      role: 'Member',
      content: 'Huazhong Univ. of Sci. & Tech., SEE B.E(2025.10)',
      },
      {
      name: 'Yichen Xiong',
      role: 'Member',
      content: 'Huazhong Univ. of Sci. & Tech., SEE B.E(2025.10)',
      },
      {
      name: 'Mingyuan Hao',
      role: 'Member',
      content: 'Huazhong Univ. of Sci. & Tech., SEE B.E(2025.10)',
      },
      {
      name: 'Jianping Huang',
      role: 'Member',
      content: 'Huazhong Univ. of Sci. & Tech., SEE B.E(2025.10)',
      },
      {
      name: 'Yayi Xiao',
      role: 'Member',
      content: 'Huazhong Univ. of Sci. & Tech., SEE B.E(2025.10)',
      },
      {
      name: 'Jiahao Huang',
      role: 'Member',
      content: 'Huazhong Univ. of Sci. & Tech., SEE B.E(2025.10)',
      },
      {
      name: 'Yilu Zhang',
      role: 'Member',
      content: 'Huazhong Univ. of Sci. & Tech., SEE B.E(2025.10)',
      },
      {
      name: 'Kechun Wang',
      role: 'Member',
      content: 'Huazhong Univ. of Sci. & Tech., SEE B.E(2025.10)',
      },
      {
      name: 'Hongyuan Liang',
      role: 'Honorary Member',
      content: 'Huazhong Univ. of Sci. & Tech., SEE PhD(2025.10)',
      },
      {
      name: 'Yuhang Cheng',
      role: 'Honorary Member',
      content: 'Huazhong Univ. of Sci. & Tech., SEE M.E(2024.6)',
      },
      {
      name: 'Xuan Li',
      role: 'Honorary Member',
      content: 'Huazhong Univ. of Sci. & Tech., SEE M.E(2024.6)',
      },
      {
      name: 'Yuanjian Chen',
      role: 'Honorary Member',
      content: 'Huazhong Univ. of Sci. & Tech., SEE M.E(2025.6)',
      },
      {
      name: 'Yeming Zheng',
      role: 'Honorary Member',
      content: 'Huazhong Univ. of Sci. & Tech., SEE PhD(2025.6)',
      },
      {
      name: 'Wutao Chen',
      role: 'Honorary Member',
      content: 'Huazhong Univ. of Sci. & Tech., SEE M.E(2025.6)',
      },
      {
      name: 'Yue Tang',
      role: 'Honorary Member',
      content: 'Huazhong Univ. of Sci. & Tech., SEE M.E(2025.6)',
      },
      {
      name: 'Yinjie He',
      role: 'Honorary Member',
      content: 'Huazhong Univ. of Sci. & Tech., SEE M.E(2025.6)',
      },
      {
      name: 'Chen Zhang',
      role: 'Honorary Member',
      content: 'Huazhong Univ. of Sci. & Tech., SEE PhD(2025.6)',
      },
      {
      name: 'Chong Ma',
      role: 'Honorary Member',
      content: 'Huazhong Univ. of Sci. & Tech., SEE M.E(2025.10)',
      },
      {
      name: 'Wenyang Li',
      role: 'Honorary Member',
      content: 'Huazhong Univ. of Sci. & Tech., SEE M.E(2025.10)',
      },
      {
      name: 'Minxuan Xu',
      role: 'Honorary Member',
      content: 'Huazhong Univ. of Sci. & Tech., SEE M.E(2025.10)',
      },
      {
      name: 'Fulin Zhou',
      role: 'Honorary Member',
      content: 'Huazhong Univ. of Sci. & Tech., SEE PhD(2025.10)',
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
