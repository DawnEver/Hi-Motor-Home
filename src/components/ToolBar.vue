<template>
    <v-card>
        <v-toolbar color="primary">
            <v-toolbar-title>
                <img src="https://cdn.jsdelivr.net/gh/Hi-Motor/Images@main/logo-latest/hi-motor_02_white.svg" alt="logo" width="100"/>
            </v-toolbar-title>
            <v-spacer />

            <v-menu open-on-hover transition="scale-transition">
                <template v-slot:activator="{ props }">
                    <v-btn v-bind="props">
                        <p>{{ $t("product") }}</p>
                    </v-btn>
                </template>
                <v-list bg-color="white">
                    <v-list-item v-for="(product, i) in products" :key="i" :href="product.link" target="_blanke">
                        <v-list-item-title>{{ product.title }}</v-list-item-title>
                    </v-list-item>
                </v-list>
            </v-menu>

            <v-btn @click="toggleLanguage">
                <v-icon size="medium">mdi-translate</v-icon>
            </v-btn>
            <v-btn @click="toggleTheme">
                <v-icon size="medium">mdi-theme-light-dark</v-icon>
            </v-btn>
        </v-toolbar>
    </v-card>
</template>

<script setup lang="ts">


const products = [
    {
        title: "Hi-Motor Designer",
        link:"https://designer.hi-motor.site",
    },
    {
        title: "Hi-Motor Hub",
        link:"https://hub.hi-motor.site",
    },
]
import { useI18n } from 'vue-i18n' // 多语言
const { locale } = useI18n() // t方法取出，t('code')使用

function toggleLanguage() {
    const currentLanguage = locale.value;
    const nextLanguage = currentLanguage === "en" ? "zhHans" : "en";
    locale.value = nextLanguage;
    if (nextLanguage === "en") {
        document.title = "Hi-Motor Product Site | Wuhan Voltworks S&T Ltd."
    } else {
        document.title = "Hi-Motor 产品官方网站 | 武汉沃特沃克科技有限公司"
    }
}
import { useTheme } from 'vuetify'

const theme = useTheme()
function toggleTheme() {
    theme.global.name.value = theme.global.current.value.dark ? 'light' : 'dark'
}
// https://juejin.cn/post/7057779411524780062
// svg颜色
</script>