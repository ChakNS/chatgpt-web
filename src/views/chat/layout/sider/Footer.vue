<script setup lang='ts'>
import { defineAsyncComponent, ref } from 'vue'
import { NImage, NxButton } from 'naive-ui'

const Setting = defineAsyncComponent(() => import('@/components/common/Setting/index.vue'))

const show = ref(false)
</script>

<template>
  <footer
    class="footer-wrapper min-w-0 p-4 overflow-hidden border-t dark:border-neutral-800"
  >
    <!-- <div class="flex-1 flex-shrink-0 overflow-hidden">
      <UserAvatar />
    </div> -->

    <!-- <HoverButton @click="show = true">
      <span class="text-xl text-[#4f555e] dark:text-white">
        <SvgIcon icon="ri:settings-4-line" />
      </span>
    </HoverButton> -->

    <NImage object-fit="contain" :show-toolbar="false" src="/code.jpg" />

    <div>
      <NxButton @click="show = true">
        设置
      </NxButton>
    </div>

    <Setting v-if="show" v-model:visible="show" />
  </footer>
</template>

<style lang="less" scoped>
.footer-wrapper {
  :deep(.n-image) {
    width: 100%;
  }
  :deep(.n-button) {
    width: 100%;
  }
}
</style>
