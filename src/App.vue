<script setup lang="ts">
import { NConfigProvider } from 'naive-ui'
import { NaiveProvider } from '@/components/common'
import { useTheme } from '@/hooks/useTheme'
import { useLanguage } from '@/hooks/useLanguage'

const { theme, themeOverrides } = useTheme()
const { language } = useLanguage()
</script>

<template>
  <NConfigProvider
    class="h-full"
    :theme="theme"
    :theme-overrides="themeOverrides"
    :locale="language"
    style="display: flex;flex-direction: column;"
  >
    <NaiveProvider>
      <RouterView />
    </NaiveProvider>
    <a style="text-align: center;color: #aaa;padding-bottom: 0.3rem;font-size: 12px;" href="https://beian.miit.gov.cn/">粤ICP备2023050095号-1</a>
  </NConfigProvider>
</template>
