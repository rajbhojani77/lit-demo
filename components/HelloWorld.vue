<template>
  <div>
    <loading-blocker :loading="loading"></loading-blocker>
    <todo-element></todo-element>
    <h1>Test</h1>
    <button @click="block">Click To Turn On Blocker This Cannot Be Clicked When Blocker Is Up</button>
  </div>
</template>

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
