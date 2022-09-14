<template>
  <div>
    composition-api
  </div>
</template>

<script lang="ts">
import { defineComponent, onMounted, PropType, getCurrentInstance } from 'vue'
import { Device } from 'mediasoup-client'
import { myContainer } from '~/libs/inversify/inversify.config'
import { TYPES } from '~/libs/inversify/types'
import { Warrior } from '~/libs/inversify/interfaces'

export default defineComponent({
  name: 'CompositionPage',
  props: {
    list: {
      type: Array as PropType<string[]>,
      default: () => []
    }
  },
  setup(props) {
    const vm = getCurrentInstance()?.proxy;

    onMounted(() => {
      console.log('onMounted', vm, props.list, new Device(), myContainer.get<Warrior>(TYPES.Warrior).fight(), vm?.$eventToObservable, vm?.$fromDOMEvent);
    })
  },
})
</script>
