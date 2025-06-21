<template>
  <v-sheet class="text-center my-10 mx-10">
    <v-row>
      <v-col>
        <img width="200" :src="logo1" alt="" />
      </v-col>
      <v-col>
        <v-row>
          <v-btn class="mx-1 mb-3" color="blue-grey-darken-2" href="mailto:hi.motor.cn@gmail.com" target="_blanke" icon>
            <img src="@/assets/footer/email-edit.svg" /></v-btn>
          <v-btn class="mx-1 mb-3" color="blue-grey-darken-2" href="https://github.com/Hi-Motor" target="_blanke" icon>
            <img src="@/assets/footer/github.svg" /></v-btn>
          <v-btn class="mx-1 mb-3" color="blue-grey-darken-2" href="https://space.bilibili.com/3546644771506195"
            target="_blanke" icon>
            <img src="@/assets/footer/bilibili.svg" /></v-btn>
          <v-btn class="mx-1 mb-3" color="blue-grey-darken-2"
            href="https://www.douyin.com/user/MS4wLjABAAAApp17tSawwMhNprsUHlUzIBWUvyt-dDcsuvQa-QRM2SnAPvDyqdCZ3mexRG6HQEJR"
            target="_blanke" icon>
            <img src="@/assets/footer/douyin.svg" /></v-btn>
          <v-btn class="mx-1 mb-3" color="blue-grey-darken-2" href="https://www.zhihu.com/people/ming-ji-zhao-yang"
            target="_blanke" icon>
            <img src="@/assets/footer/zhihu.svg" /></v-btn>
          <v-btn class="mx-1 mb-3" color="blue-grey-darken-2"
            href="https://www.xiaohongshu.com/user/profile/68445b7e000000001b023a82" target="_blanke" icon>
            <img src="@/assets/footer/xiaohongshu.svg" /></v-btn>
        </v-row>
        <v-row>
          <p class="text-left">
            Hi-Motor © {{ $t("copyrights") }}
            <br />
            <a href="mailto:hi.motor.cn@gmail.com" rel="noreferrer" target="_blank">hi.motor.cn@gmail.com</a>
          <div v-if="$i18n.locale === 'zhHans'">
            <img src="@/assets/footer/mps.png" height="12pt">
            <a href="https://beian.mps.gov.cn/#/query/webSearch?code=32118202001102" rel="noreferrer"
              target="_blank">苏公网安备32118202001102号</a>
            <br />
            <a href="https://beian.miit.gov.cn/">苏ICP备2025180711号</a>
          </div>
          </p>
        </v-row>
      </v-col>
    </v-row>
  </v-sheet>
</template>

<script setup lang="ts">

const logoSvg = "https://oss.hi-motor.site/web/logo/hi-motor.svg"
const logoLightSvg = "https://oss.hi-motor.site/web/logo/hi-motor_white.svg"

import { computed } from 'vue'
import { useTheme } from 'vuetify'
const theme = useTheme()
const logo1 = computed(() => {
  if (theme.global.name.value === 'light') {
    return logoSvg
  }
  else {

    return logoLightSvg
  }
})

</script>
