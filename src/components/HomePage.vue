<template>
  <ToolBar />
  <Hero />
  <Products />
  <Milestones />
  <Members />
  <Collaborators />
  <v-divider />
  <Footer />
</template>

<script setup lang="ts">
import ToolBar from '@/components/ToolBar.vue';
import Hero from '@/components/Hero.vue';
import Products from '@/components/Products.vue';
import Milestones from '@/components/Milestones.vue';
import Members from '@/components/Members.vue'
import Collaborators from '@/components/Collaborators.vue'
import Footer from '@/components/Footer.vue';
</script>