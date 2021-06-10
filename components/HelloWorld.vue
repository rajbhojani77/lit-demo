<template>
  <div>
    <loading-blocker :loading="loading"></loading-blocker>
    <h1>Test</h1>
    <button @click="block">Click To Turn On Blocker This Cannot Be Clicked When Blocker Is Up</button>
  </div>
</template>
<script type="module">
import {loading-blocker} from '@/loading-blocker.js';
</script>

<script>

const delay = ms => new Promise(resolve => setTimeout(resolve, ms));

export default {
  data: () => ({ loading: false }),
  methods: {
    async block () {
      this.loading = true
      await delay(2000)
      this.loading = false
    }
  }
}
</script>
