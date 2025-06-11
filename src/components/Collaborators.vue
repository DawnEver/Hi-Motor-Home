
<template>
  <v-sheet class="mx-auto my-10">

      <h1 :class="`${titleClass} font-weight-black`" align="center">
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
import hustFig from "@/assets/collaborators/hust.svg"
import hustWhiteFig from "@/assets/collaborators/hust-white.svg"
import marathonFig from "@/assets/collaborators/marathon.png"
import marathonWhiteFig from "@/assets/collaborators/marathon-white.png"
import nottinghamFig from "@/assets/collaborators/nottingham.png"
import nottinghamWhiteFig from "@/assets/collaborators/nottingham-white.png"

import useResponsiveFonts from '@/composables/useResponsiveFonts';
const {titleClass,
    itemTitleClass,
    cardTitleClass,
    cardTextClass,
    cardActionClass} = useResponsiveFonts()

const theme = useTheme()
const logos = computed(() => {
  if (theme.global.name.value === 'light') {
    return [
      {
        id: 1,
        name: "hust",
        logoUrl: hustFig,
        link: "https://www.hust.edu.cn",
      },
      {
        id: 2,
        name: "marathon",
        logoUrl: marathonFig,
        link: "https://www.regalrexnord.com",
      },
      {
        id: 3,
        name: "nottingham",
        logoUrl: nottinghamFig,
        link: "https://www.nottingham.ac.uk",
      },
    ]
  }
  else {
    return [
      {
        id: 1,
        name: "hust",
        logoUrl: hustWhiteFig,
        link: "https://www.hust.edu.cn",
      },
      {
        id: 2,
        name: "marathon",
        logoUrl: marathonWhiteFig,
        link: "https://www.regalrexnord.com",
      },
      {
        id: 3,
        name: "nottingham",
        logoUrl: nottinghamWhiteFig,
        link: "https://www.nottingham.ac.uk",
      },
    ]
  }
})

</script>
