<template>
    <v-card>
        <v-toolbar color="primary">
            <v-toolbar-title>
                <img src="https://oss.hi-motor.site/web/logo/hi-motor_white.svg" alt="logo" width="60" />
            </v-toolbar-title>
            <v-spacer />

            <v-menu open-on-hover transition="scale-transition">
                <template v-slot:activator="{ props }">
                    <v-btn v-bind="props" :class="cardTitleClass">
                        <p>{{ $t("product") }}</p>
                    </v-btn>
                </template>
                <v-list bg-color="white">
                    <v-list-item v-for="(product, i) in products" :key="i" :href="product.link" target="_blanke">
                        <v-list-item-title :class="itemTitleClass">{{ product.title }}</v-list-item-title>
                    </v-list-item>
                </v-list>
            </v-menu>

            <v-btn @click="toggleLanguage">
                <v-icon>mdi-translate</v-icon>
            </v-btn>
            <v-btn @click="toggleTheme">
                <v-icon>mdi-theme-light-dark</v-icon>
            </v-btn>
        </v-toolbar>
    </v-card>
</template>

<script setup lang="ts">
import useResponsiveFonts from '@/composables/useResponsiveFonts';
const { titleClass,
    itemTitleClass,
    cardTitleClass,
    cardTextClass,
    cardActionClass } = useResponsiveFonts();

const products = [
    {
        title: "Hi-Motor Designer",
        link: "https://designer.hi-motor.site",
    },
    {
        title: "Hi-Motor Hub",
        link: "https://hub.hi-motor.site",
    },
]
import { useI18n } from 'vue-i18n' // 多语言
const { locale } = useI18n() // t方法取出，t('code')使用

import { useRouter } from 'vue-router';
const router = useRouter();

function toggleLanguage() {
    const currentLanguage = locale.value;
    const nextLanguage = currentLanguage === "en" ? "zhHans" : "en";
    locale.value = nextLanguage;
    if (nextLanguage === "en") {
        document.title = "Hi-Motor | Motor Design"
        router.push('/#en');
    } else {
        document.title = "Hi-Motor | 电机设计"
        router.push('/');
    }
}
import { useTheme } from 'vuetify'

const theme = useTheme()
function toggleTheme() {
    theme.global.name.value = theme.global.current.value.dark ? 'light' : 'dark'
}

import { useRoute } from 'vue-router';
import { watch } from 'vue';

const route = useRoute();

watch(
    () => route.path,
    (newPath) => {
        if (newPath.startsWith('/#en')) {
            locale.value = 'en';
            document.title = "Hi-Motor | Motor Design";
        } else {
            locale.value = 'zhHans';
            document.title = "Hi-Motor | 电机设计";
        }
    },
    { immediate: true }
);
// https://juejin.cn/post/7057779411524780062
// svg颜色
</script>