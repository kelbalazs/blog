<template>
  <PatchMeta />
  <NavBar
    :title="'📝 vue3-md-blog'"
    :sections="blogSections"
  />
  <Suspense>
    <template #default>
      <router-view />
    </template>
    <template #fallback>
      <Loader />
    </template>
  </Suspense>
  <Footer />
</template>

<script setup lang="ts">
import { inject } from 'vue'
import PatchMeta from './components/PatchMeta.vue'
import Loader from './components/Loader.vue'
import NavBar from './components/NavBar.vue'
import Footer from './components/Footer.vue'
import 'bootstrap/dist/css/bootstrap.css'

const blogSections = inject('blogSections', {})
</script>
