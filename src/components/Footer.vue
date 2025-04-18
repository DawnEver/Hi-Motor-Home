
<template>
<v-sheet class="text-center my-10 mx-10">
    <v-col>
      <v-row>
        <v-btn class="mx-1 mb-3" color="blue-grey-darken-2" href="mailto:hi.motor.cn@gmail.com" target="_blanke" icon>
          <v-icon>mdi-email-edit</v-icon></v-btn>
        <v-btn class="mx-1 mb-3" color="blue-grey-darken-2" href="https://weixin.qq.com" target="_blanke" icon>
          <v-icon>mdi-wechat</v-icon></v-btn>
        <v-btn class="mx-1 mb-3" color="blue-grey-darken-2"  href="https://github.com/Hi-Motor" target="_blanke" icon>
          <v-icon>mdi-github</v-icon></v-btn>
        <v-btn class="mx-1 mb-3" color="blue-grey-darken-2" href="https://bilibli.com" target="_blanke" icon>
          <img src="@/assets/bilibili.svg" /></v-btn>
      </v-row>
      <v-row>
        <p class="text-left">
          Hi-Motor © {{ $t("copyrights") }}
          <br />
          <a href="mailto:hi.motor.cn@gmail.com" rel="noreferrer" target="_blank">hi.motor.cn@gmail.com</a>
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
</v-sheet>
</template>

<script setup lang="ts">

const logoSvg = "https://cdn.jsdelivr.net/gh/Hi-Motor/Images@main/logo-latest/hi-motor_02.svg"
const logoLightSvg = "https://cdn.jsdelivr.net/gh/Hi-Motor/Images@main/logo-latest/hi-motor_02_white.svg"

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
