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
      h('span', { class: 'ml-1.5' }, '我决定关闭这个站点了 !!!'),
    ]),
    description: () => h('div', { class: 'flex flex-col' }, [
      h('span', { class: 'text-gray-800 dark:text-white mt-2' }, '斯密马赛 🥲'),
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
      h('span', { class: 'text-gray-800 dark:text-white mt-1' }, '各位可以考虑去使用官方的chatgpt，那是完全免费的'),
      h('span', { class: 'text-gray-800 dark:text-white mt-1' }, '关于账号注册教程可以参考这篇博客，对于其中碰到的问题可以直接留言 or 联系我'),
      h('a', {
        class: 'text-blue-400',
        href: 'https://takina.ink/477/',
        target: '_blank',
      }, 'https://takina.ink/477/'),
      h('span', { class: 'text-gray-800 dark:text-white mt-4' }, '或者转到我搭建的小程序，这边我会一直维护'),
      h('img', {
        class: 'h-24 w-24 object-cover rounded-md mt-1.5',
        src: 'https://takina.ink/wp-content/uploads/2023/03/6u7M6kbC45lTEWEFH84C.jpg',
      }),
      h('span', { class: 'text-gray-800 dark:text-white mt-4' }, 'WEB端的话，后续我大概会自费建一个站，毕竟我自己也得用，但是可能不会开放给太多人，问就是钱包遭不住 🤣（之前有V过我cola的同学如果还需要使用的话可以联系我'),
      h('span', { class: 'text-gray-800 dark:text-white mt-2' }, '然后我还拉了一个GPT的讨论群，有需要的话各位可加群'),
      h('img', {
        class: 'w-56 object-cover rounded-md mt-1.5',
        src: 'https://image.qwq.link/images/2023/03/31/E9006C0B-B957-3530-37A3-9E03B5223E24.jpg',
      }),
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
  });
  (window.$notification as any).create({
    title: () => h('div', [
      h('span', { class: 'text-green-500' }, '#'),
      h('span', { class: 'ml-1.5' }, '以下是恰饭内容 👀'),
    ]),
    description: () => h('div', { class: 'flex flex-col' }, [
      h('span', { class: 'text-gray-800 dark:text-white mt-1' }, '如果觉得小程序不够方便，且懒得翻墙，也不愿意使用官方的CHATGPT，这里我提供两种方案'),
      h('span', { class: 'text-gray-800 dark:text-white mt-2' }, '1️⃣ 部署在你的服务器上'),
      h('li', { class: 'text-gray-800 dark:text-white mt-1' }, '需要是香港服务器'),
      h('li', { class: 'text-gray-800 dark:text-white mt-1' }, '需要准备一个域名（不至于直接展示IP吧 🫠'),
      h('li', { class: 'text-gray-800 dark:text-white mt-1' }, '然后坐等搭建完成'),
      h('span', { class: 'text-gray-800 dark:text-white mt-5' }, '2️⃣ 部署在我的服务器上'),
      h('li', { class: 'text-gray-800 dark:text-white mt-1' }, '由我进行维护'),
      h('li', { class: 'text-gray-800 dark:text-white mt-1' }, '由我提供一个二级域名供你进行访问'),
      h('li', { class: 'text-gray-800 dark:text-white mt-1' }, '并提供一个站点密码'),
      h('span', { class: 'text-gray-800 dark:text-white mt-5' }, '有需要的可以联系我'),
      h('img', {
        class: 'w-56 object-cover rounded-md mt-1.5',
        src: 'https://image.qwq.link/images/2023/03/31/681A8A87-7450-7F90-D066-DFF0B8CF0C05.jpg',
      }),
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
