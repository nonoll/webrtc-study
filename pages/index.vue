<template>
  <div>
    <Tutorial />
  </div>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  name: 'IndexPage',
  mounted() {
    console.log('mounted', this);
  }
})
</script>
