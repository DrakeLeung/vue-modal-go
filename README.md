# vue-modal-go

> a modal component for vue

## Install
```bash
npm i --save vue-modal-go
```

## Quick Start
You can pass some property(`is-open`, `close-timeout-ms`...) to the `modal` component.

**More Properties just check out the [API docs](./docs/README.md)**.

```html
// App.vue

<template>
  <modal
    :is-open=true
    :close-timeout-ms=0
    :should-close-on-overlay-click=true
    :on-request-close="greet"
    :custom-style="{ backgroundColor: '#fff' }"
  >
    <h1>Hello World</h1>
    <p> “Don't cry because it's over, smile because it happened.” </p>
  </modal>
</template>

<script>
import Modal from 'vue-modal-go'

export default {
  components: { Modal },
  methods: {
    greet() {
      console.log('Hello world')
    }
  },
}
</script>
```

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# run example, then visit: localhost:8080/example/index.html
npm run example

# build for production with minification
npm run build
```
