<template lang="pug">
.app-lists
  ul.flex.gap-8
    li(v-for='list in lists', :key='list.id')
      nuxt-link.transition.text-red-600--hover(:to='list.path') {{ list.name }}
</template>

<script lang="ts">
import { Component, Vue, Prop } from 'vue-property-decorator'

interface List {
  name: string
  path: string
}

@Component
export default class AppLists extends Vue {
  message: string = 'This is a message'

  @Prop()
  lists!: List
}
</script>

<style lang="scss"></style>
