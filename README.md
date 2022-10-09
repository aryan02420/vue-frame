# VueFrame

Render your Vue nodes in an iframe

## Installation

```bash
npm i vue-frame
```

> Vue3 is a peer dependency and needs to be installed separately

## Usage

```vue
<script setup lang="ts">
import { VueFrame } from 'vue-frame'
</script>

<template>
  <vue-frame>
    <h1>Hello Wrold!</h1>
  </vue-frame>
</template>
```

### Props

#### inherit-styles

`inheritStyles: Boolean`

If `true`, styles from parent window will be copied into the iframe. Use this to make the iframe look like your Vue app.

#### stylesheet

`stylesheet: String`

If set, it will create a new style tag using this value. Use this for injecting custom styles into the iframe.

#### All properties of [HTMLIFrameElement](https://developer.mozilla.org/en-US/docs/Web/API/HTMLIFrameElement)

## Demo

https://aryan02420.github.io/vue-frame
