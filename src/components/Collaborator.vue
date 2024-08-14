
<template>
  <v-sheet elevation="0" color="transparent" class="mx-auto my-10">

      <h1 class="font-weight-black text-h3 pb-2" align="center">
        {{ $t("collaborator") }}
      </h1>

      <v-row align="center" justify="center">
        <v-col sm="6" md="4" lg="3" v-for="logo in logos">
          <v-card 
          flat
          :href="logo.link"
          >
            <v-img height="60" :src="logo.logoUrl"/>
          </v-card>
        </v-col>
      </v-row>
  </v-sheet>
</template>


<script setup lang="ts">
import { computed } from 'vue'
import { useTheme } from 'vuetify'
import hustSvg from "@/assets/hust.svg"
import hustLightSvg from "@/assets/hust-light.svg"
import regalSvg from "@/assets/regal.svg"
import regalLightSvg from "@/assets/regal-light.svg"
const theme = useTheme()
const logos = computed(() => {
  if (theme.global.name.value === 'light') {
    return [
      {
        id: 1,
        name: "hust",
        logoUrl: hustSvg,
        link: "https://www.hust.edu.cn/",
      },{
        id: 2,
        name: "regal",
        logoUrl: regalSvg,
        link: "https://www.regalrexnord.com/",
      },
    ]
  }
  else {
    return [
      {
        id: 1,
        name: "hust",
        logoUrl: hustLightSvg,
        link: "https://www.hust.edu.cn/",
      },{
        id: 2,
        name: "regal",
        logoUrl: regalLightSvg,
        link: "https://www.regalrexnord.com/",
      },
    ]
  }
})

</script>
