<script setup lang="ts">
import { NConfigProvider, NDivider } from 'naive-ui'
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
      h('span', { class: 'ml-1.5' }, '我决定关闭这个站点了 !!!'),
    ]),
    description: () => h('div', { class: 'flex flex-col' }, [
      h('span', { class: 'text-gray-800 dark:text-white mt-2' }, '18刀额度用完了，重新注册的账号免费额度只有5刀，按照当下的使用量，差不多四天不到就没了 🥲'),
      h('img', {
        class: 'w-full object-cover rounded-md mt-1.5',
        src: 'https://image.qwq.link/images/2023/03/31/QQ20230331-1018082x.png',
      }),
      h('img', {
        class: 'w-full object-cover rounded-md mt-1.5',
        src: 'https://image.qwq.link/images/2023/03/31/QQ20230331-1025002x.png',
      }),
      h('span', { class: 'text-gray-800 dark:text-white mt-4' }, '原本想一直白嫖新号额度来运营这个站，OpenAI改策略了那就没办法了，只有5刀的话申请以及换号都太频繁了，且麻烦，所以我先run了，有缘再见 😎'),
      h('span', { class: 'text-gray-800 dark:text-white mt-1' }, '当然是在新号的5刀用完之后 😎'),
      h('span', { class: 'text-gray-800 dark:text-white mt-1' }, '然后我拉了一个关于GPT的qq群'),
      h('span', { class: 'text-gray-800 dark:text-white mt-1' }, '🐧 227191172'),
    ]),
    // description: () => h('div', { class: 'flex flex-col' }, [
    //   h('span', { class: 'text-gray-800 dark:text-white' }, '该站域名'),
    //   h('a', {
    //     class: 'text-blue-400',
    //     href: 'https://gpt.takina.ink',
    //     target: '_blank',
    //   }, 'https://gpt.takina.ink'),
    //   h('a', {
    //     class: 'text-blue-400',
    //     href: 'https://yu1.cc',
    //     target: '_blank',
    //   }, 'https://yu1.cc'),
    //   h('span', { class: 'text-gray-800 dark:text-white mt-3' }, '该站基于开源项目 chatgpt-web，至于域名有两个，且对外放的不是 yu1.cc，是因为其被微信给拿下了😰（注册前，真不是我干的 😭），需要注意的是其记录并不互通 ！！！'),
    //   h('span', { class: 'text-gray-800 dark:text-white mt-2' }, '另外，我也整了个小程序，欢迎各位使用捏 🤗'),
    //   h('img', {
    //     class: 'h-24 w-24 object-cover rounded-md mt-1.5',
    //     src: 'https://takina.ink/wp-content/uploads/2023/03/6u7M6kbC45lTEWEFH84C.jpg',
    //   }),
    //   h('span', { class: 'text-gray-800 dark:text-white mt-2' }, '📝 留言 & 建议请转到博客'),
    //   h('a', {
    //     class: 'text-blue-400',
    //     href: 'https://takina.ink',
    //     target: '_blank',
    //   }, 'https://takina.ink'),
    //   h('span', { class: 'text-gray-800 dark:text-white mt-1' }, '🎈 关于搭建上的问题，我也可以提供力所能及的帮助'),
    //   h('span', { class: 'text-gray-800 dark:text-white mt-1' }, '🎈 然后还拉了一个QQ群'),
    //   h('span', { class: 'text-gray-800 dark:text-white mt-1' }, '🎈 227191172'),
    //   h(NDivider),
    //   h('span', { class: 'text-gray-800 dark:text-white' }, '🥤 如果你觉得对你有帮助，可以考虑V我一罐可乐'),
    //   h('span', { class: 'text-gray-800 dark:text-white' }, '😙 非常感谢！'),
    //   h('img', {
    //     class: 'w-56 object-cover rounded-md mt-1.5',
    //     src: 'https://image.qwq.link/images/2023/03/23/WechatPay.png',
    //   }),
    // ]),
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
