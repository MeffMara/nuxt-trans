<template lang="pug">
#app
  AppHeader
  Nuxt(:text='message')
</template>

<script lang="ts">
import { defineComponent, ref } from '@vue/composition-api'
// interface User {
//   firstName: string
//   lastName: string
// }

export default defineComponent({
  // props: {
  //   user: {
  //     type: Object as () => User,
  //     required: true,
  //   },
  // },

  setup() {
    const message = ref('This is a message')

    return {
      message,
    }
  },
})
</script>

<style lang="scss"></style>
