<script setup lang="ts">
import { NConfigProvider } from 'naive-ui'
import { onMounted } from 'vue'
import { NaiveProvider } from '@/components/common'
import { useTheme } from '@/hooks/useTheme'
import { useLanguage } from '@/hooks/useLanguage'

const { theme, themeOverrides } = useTheme()
const { language } = useLanguage()

onMounted(() => {
  // (window.$notification as any).create({
  //   title: () => h('div', [
  //     h('span', { class: 'text-green-500' }, '#'),
  //     h('span', { class: 'ml-1.5' }, '以下是恰饭内容 👀'),
  //   ]),
  //   description: () => h('div', { class: 'flex flex-col' }, [
  //     h('span', { class: 'text-gray-800 dark:text-white mt-1' }, '如果觉得小程序不够方便，且懒得翻墙，也不愿意使用官方的CHATGPT，这里我提供两种方案'),
  //     h('span', { class: 'text-gray-800 dark:text-white mt-2' }, '1️⃣ 部署在你的服务器上'),
  //     h('li', { class: 'text-gray-800 dark:text-white mt-1' }, '需要是香港服务器'),
  //     h('li', { class: 'text-gray-800 dark:text-white mt-1' }, '需要准备一个域名（不至于直接展示IP吧 🫠'),
  //     h('li', { class: 'text-gray-800 dark:text-white mt-1' }, '然后坐等搭建完成'),
  //     h('span', { class: 'text-gray-800 dark:text-white mt-5' }, '2️⃣ 部署在我的服务器上'),
  //     h('li', { class: 'text-gray-800 dark:text-white mt-1' }, '由我进行维护'),
  //     h('li', { class: 'text-gray-800 dark:text-white mt-1' }, '由我提供一个二级域名供你进行访问'),
  //     h('li', { class: 'text-gray-800 dark:text-white mt-1' }, '并提供一个站点密码'),
  //     h('span', { class: 'text-gray-800 dark:text-white mt-5' }, '有需要的可以联系我'),
  //     h('img', {
  //       class: 'w-56 object-cover rounded-md mt-1.5',
  //       src: 'https://image.qwq.link/images/2023/03/31/681A8A87-7450-7F90-D066-DFF0B8CF0C05.jpg',
  //     }),
  //   ]),
  // })
})
</script>

<template>
  <NConfigProvider
    class="h-full"
    :theme="theme"
    :theme-overrides="themeOverrides"
    :locale="language"
  >
    <NaiveProvider>
      <RouterView />
    </NaiveProvider>
  </NConfigProvider>
</template>
