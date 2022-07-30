<template>
  <Led state="true" size="32" />
  <Led state="false" size="64" />
  <Led :state="state" size="128" />
</template>

<script>
import { defineComponent, ref, onMounted, onBeforeUnmount } from 'vue'
import { useTimer } from '@padcom/virtualcpu-common-vue-timer'

import Led from './components/Led.vue'

export default defineComponent({
  components: {
    Led,
  },
  setup() {
    const state = ref(false)
    useTimer(() => state.value = !state.value)

    return { state }
  },
})
</script>
