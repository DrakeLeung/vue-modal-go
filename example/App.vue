<template>
  <modal
    :is-open=true
    :close-timeout-ms=0
    :should-close-on-overlay-click=true
    :on-request-close="greet"
    :custom-style="{ backgroundColor: '#ff4210' }"
  >
    <h1>Hello World</h1>
  </modal>
</template>

<script>
import Modal from '../src'

export default {
  components: { Modal },
  methods: {
    greet() {
      console.log('Hello world')
    }
  },
}
</script>