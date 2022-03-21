<template lang="pug">
header.app-header
  .top.grid.grid-cols-4.max-w-screen-xl.m-auto.items-center.gap-8
    LogoIcon.col-auto
    nav.app-header__nav
      AppLists(:lists='lists')
    .search.ml-auto
      form(action='', method='method')
        label.relative
          input.border.border-indigo-600.main-text.pr-8.pl-4.bg-light-gray(
            type='text',
            placeholder='Пошук'
          )
          .absolute.top-0.right-5(@click.stop='clickMe')
            SearchIcon
    a.btn.btn--red.text-3xl.text-white.btn--bold(href='tel:044 250 83-38') 044 250 83-38
  .bottom.flex.max-w-screen-xl.m-auto.items-center.grid-cols-3.gap-8
    .text-2xl.flex.text-red.items-center.gap-2
      MapMarker
      | м.Київ
    nav.app-header__nav
      AppLists(:lists='menu')
    nuxt-link.btn.ml-auto.flex.gap-3(to='/user')
      UserIcon
      | Особовий кабінет
</template>

<script lang="ts">
import { defineComponent, computed, ref } from '@vue/composition-api'
import LogoIcon from '~/components/icon/LogoSite.vue'
import SearchIcon from '~/components/icon/SearchIcon.vue'
import UserIcon from '~/components/icon/UserIcon.vue'
import MapMarker from '~/components/icon/MapMarker.vue'

export default defineComponent({
  components: { LogoIcon, SearchIcon, UserIcon, MapMarker },
  // props: {
  //   user: {
  //     type: Object as () => User,
  //     required: true,
  //   },
  // },

  setup() {
    const lists = [
      {
        id: Math.floor(Math.random() * 9999999),
        name: 'Бізнес',
        path: '/business',
      },
      {
        id: Math.floor(Math.random() * 9999999),
        name: 'Приватним особам',
        path: '/private-person',
      },
    ]

    const menu = [
      {
        id: Math.floor(Math.random() * 9999999),
        name: 'Про Компанію',
        path: '/about',
      },
      {
        id: Math.floor(Math.random() * 9999999),
        name: 'Послуги',
        path: '/services',
      },
      {
        id: Math.floor(Math.random() * 9999999),
        name: 'Напрямок',
        path: '/road',
      },
      {
        id: Math.floor(Math.random() * 9999999),
        name: 'Тарифи',
        path: '/price',
      },
      {
        id: Math.floor(Math.random() * 9999999),
        name: 'Партнерам',
        path: '/partners',
      },
      {
        id: Math.floor(Math.random() * 9999999),
        name: 'Питання',
        path: '/question',
      },
      {
        id: Math.floor(Math.random() * 9999999),
        name: 'Зв`язатися',
        path: '/contacts',
      },
    ]
    const message = ref('This is a message')
    const clickMe = () => {
      alert('click')
    }
    return {
      message,
      clickMe,
      lists,
      menu,
    }
  },
})
</script>

<style scoped>
</style>
