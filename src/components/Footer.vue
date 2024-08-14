
<template>
  <v-sheet elevation="0" class="mx-auto landing-warpper" rounded>
    <v-container class="text-center pa-10">
  <v-sheet class="mx-auto" color="transparent" elevation="0" max-width="1600">
    <v-row>
      <v-col>
        <img width="150" :src="logo1" alt="" />
      </v-col>
      <v-col>
        <v-row>
          <v-btn class="mx-1 mb-3" color="blue-grey-darken-2" href="mailto:contact@mail.voltworks.cn" target="_blanke" icon>
            <v-icon>mdi-email-edit</v-icon></v-btn>
          <v-btn class="mx-1 mb-3" color="blue-grey-darken-2" href="https://weixin.qq.com" target="_blanke" icon>
            <v-icon>mdi-wechat</v-icon></v-btn>
          <v-btn class="mx-1 mb-3" color="blue-grey-darken-2"  href="https://github.com/Hi-Motor" target="_blanke" icon>
            <v-icon>mdi-github</v-icon></v-btn>
          <v-btn class="mx-1 mb-3" color="blue-grey-darken-2" href="https://bilibli.com" target="_blanke" icon>
            <img src="@/assets/bilibili.svg" /></v-btn>
        </v-row>
        <v-row>
          <p class="text-right">
            Hi-Motor © {{ $t("copyrights") }}
          <div v-if="$i18n.locale === 'zhHans'">
            <img src="@/assets/mps.png" height="12pt">
              <a href="https://beian.mps.gov.cn/#/query/webSearch?code=42018502007318" rel="noreferrer"
                target="_blank">鄂公网安备42018502007318</a>
              <br />
              <!-- 
              <img src="@/assets/mps.png" height="12pt">
              <a href="https://beian.mps.gov.cn/#/query/webSearch?code=42018502007306" rel="noreferrer"
                target="_blank">鄂公网安备42018502007306</a>
              <br /> 
              -->
              <a href="https://beian.miit.gov.cn/">鄂ICP备2024034308号</a>
          </div>
          </p>
        </v-row>
      </v-col>
    </v-row>
  </v-sheet>
</v-container>
</v-sheet>
</template>

<script setup lang="ts">

const logo1Svg = "https://cdn.jsdelivr.net/gh/Hi-Motor/Images@main/logo-latest/hi-motor_01.svg"
const logo1LightSvg = "https://cdn.jsdelivr.net/gh/Hi-Motor/Images@main/logo-latest/hi-motor_01_white.svg"

import { computed } from 'vue'
import { useTheme } from 'vuetify'
const theme = useTheme()
const logo1 = computed(() => {
  if (theme.global.name.value === 'light') {
    return logo1Svg
  }
  else {

    return logo1LightSvg
  }
})

</script>
