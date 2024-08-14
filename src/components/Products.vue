<template>
  <v-sheet elevation="0" color="transparent" class="ml-2 my-10">

    <h1 class="font-weight-black text-h3 pb-2" align="center">
      {{ $t("product") }}
    </h1>
    <v-container>
      <v-tabs v-model="tab" color="primary">
        <v-tab :value="product.id" v-for="product in products" :key="product.id">
          <v-icon start>
            {{ product.icon }}
          </v-icon>
          {{ product.name }}
        </v-tab>

      </v-tabs>
      <v-window v-model="tab">
        <v-window-item :value="product.id" v-for="product in products" :key="product.id">
          <v-card flat class="ml-10">
            <v-card-text>
              <v-container align="center">
                <img :src="product.imgUrl" width=100% />
              </v-container>
              {{ product.description }}
            </v-card-text>
            <v-card-actions>
              <v-btn :href="product.href">{{ $t("learnMore") }}
                <v-icon>mdi-open-in-new</v-icon></v-btn>
            </v-card-actions>
          </v-card>
        </v-window-item>
      </v-window>
  </v-container>
  </v-sheet>
</template>

<script setup lang="ts">
import { computed } from 'vue';
import { ref } from 'vue'
import { useI18n } from 'vue-i18n'

const productHMDZh = "https://cdn.jsdelivr.net/gh/Hi-Motor/Images@main/hi-motor-designer/hmd_model_zh.jpg"
const productHMDEn = "https://cdn.jsdelivr.net/gh/Hi-Motor/Images@main/hi-motor-designer/hmd_model_en.jpg"
const productHMH = "https://cdn.jsdelivr.net/gh/Hi-Motor/Images@main/hi-motor-hub/hmh.jpg"

const { locale } = useI18n()
const tab = ref('0')
const products = computed(() => {
  const lang = locale.value;
  if (lang === "zhHans") {
    return [
      {
        id: 1,
        name: "Hi-Motor Designer",
        icon: "mdi-engine",
        description: "Hi-Motor Designer 是新一代电机设计智能助手。\
          在这里，用户可以从零开始设计一台电机，从参数化建模、有限元仿真到性能优化...\
          探索高性能电机的奥秘。",
        href: "https://designer.hi-motor.site",
        imgUrl: productHMDZh,
      },
      {
        id: 2,
        name: "Hi-Motor Hub",
        icon: "mdi-magnify",
        description: "Hi-Motor Hub 是一个电机设计知识库，\
          容纳当前主流电机企业全型号高性能电机。\
          无论是电机设计工程师，还是采购人员，\
          都可以在这里获取需要的信息。",
        href: "https://hub.hi-motor.site",
        imgUrl: productHMH,
      }
    ]
  } else {
    return [
      {
        id: 1,
        name: "Hi-Motor Designer",
        icon: "mdi-engine",
        description: "As your new generation of motor design intelligent asistant, \
          Hi-Motor Designer provides a complete workflow of design and optimization of high-level motors, \
          including parametric modelling, FEM simulation and performance optimization.",

        href: "https://designer.hi-motor.site",
        imgUrl: productHMDEn,
      },
      {
        id: 2,
        name: "Hi-Motor Hub",
        icon: "mdi-magnify",
        description: "Hi-Motor Hub is a knowledge base for motor design, \
          which contains all mainstream high-performance motors of current motor enterprises. \
          Whether you are a motor design engineer or a procurement officer, \
          you can get the information you need here.",
        href: "https://hub.hi-motor.site",
        imgUrl: productHMH,
      }
    ]
  }

})
</script>