<template>
  <div>
    decorator
  </div>
</template>

<script lang="ts">
import {
  Component,
  Prop,
  Vue
} from "nuxt-property-decorator"
import { Device } from 'mediasoup-client'
import { myContainer } from '~/libs/inversify/inversify.config'
import { TYPES } from '~/libs/inversify/types'
import { Warrior } from '~/libs/inversify/interfaces'

@Component({})
export default class DecoratorPage extends Vue {
  @Prop({ default: () => [] })
  list!: Array<string>

  mounted() {
    console.log('mounted', this, this.list, new Device(), myContainer.get<Warrior>(TYPES.Warrior).fight());
  }
}
</script>
