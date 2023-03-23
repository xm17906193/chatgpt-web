<script setup lang="ts">
import { NConfigProvider } from 'naive-ui'
import { h, onMounted } from 'vue'
import { NaiveProvider } from '@/components/common'
import { useTheme } from '@/hooks/useTheme'
import { useLanguage } from '@/hooks/useLanguage'

const { theme, themeOverrides } = useTheme()
const { language } = useLanguage()

onMounted(() => {
  (window.$notification as any).create({
    title: () => h('div', [
      h('span', { class: 'text-green-500' }, '#'),
      h('span', { class: 'ml-1.5' }, 'Tips'),
    ]),
    description: () => h('div', { class: 'flex flex-col' }, [
      h('span', { class: 'text-gray-800 dark:text-white' }, '该站基于开源项目 chatgpt-web'),
      h('a', {
        class: 'text-blue-400',
        href: 'https://github.com/Chanzhaoyu/chatgpt-web',
        target: '_blank',
      }, 'https://github.com/Chanzhaoyu/chatgpt-web'),
      h('span', { class: 'text-gray-800 dark:text-white mt-2' }, '另外，我也整了个小程序，欢迎各位使用捏 😙'),
      h('img', {
        class: 'h-24 w-24 object-cover rounded-md mt-1.5',
        src: 'https://takina.ink/wp-content/uploads/2023/03/6u7M6kbC45lTEWEFH84C.jpg',
      }),
      h('span', { class: 'text-gray-800 dark:text-white mt-2' }, '📝 留言 & 建议请转到博客'),
      h('a', {
        class: 'text-blue-400',
        href: 'https://takina.ink',
        target: '_blank',
      }, 'https://takina.ink'),
      h('span', { class: 'text-gray-800 dark:text-white mt-1' }, '🎈 关于搭建上的问题，我也可以提供一定的帮助'),
      // h(NDivider),
      // h('span', { class: 'text-gray-800 dark:text-white' }, '🤗 如果你觉得站点对你有帮助，可以考虑V我一瓶可乐'),
      // h('img', {
      //   class: 'h-24 w-24 object-cover rounded-md mt-1.5',
      //   src: 'https://takina.ink/wp-content/uploads/2023/03/6u7M6kbC45lTEWEFH84C.jpg',
      // }),
    ]),
  })
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
