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
const slides = [
    {
        imgUrl: "https://oss.hi-motor.site/web/cover/cover_01.jpg",
    },
    {
        imgUrl: "https://oss.hi-motor.site/web/cover/cover_02.jpg",
    },
    {
        imgUrl: "https://oss.hi-motor.site/web/cover/cover_03.jpg",
    },
]
</script>