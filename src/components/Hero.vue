<template>
    <v-carousel cycle height="100%" hide-delimiter-background show-arrows="hover">
        <v-carousel-item v-for="(slide, i) in slides" :key="i">
            <div class="d-flex fill-height justify-center align-center">
                <v-img :src="slide.imgUrl" contain max-height="1000" />
            </div>

        </v-carousel-item>
    </v-carousel>
</template>

<script setup lang="ts">
import cover_01 from "@/assets/hero/cover_01.jpg";
import cover_02 from "@/assets/hero/cover_02.jpg";
import cover_03 from "@/assets/hero/cover_03.jpg";
import cover_04 from "@/assets/hero/cover_04.jpg";
const slides = [
    {
        imgUrl: cover_01,
    },
    {
        imgUrl: cover_02,
    },
    {
        imgUrl: cover_03,
    },
    {
        imgUrl: cover_04,
    },
]
</script>