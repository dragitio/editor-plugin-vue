<p align="center">
  <a href="https://dragit.io" target="_blank" rel="noopener noreferrer">
    <img width="180" src="https://dragit.io/img/logo_fb_developer.jpg" alt="Dragit logo">
  </a>
</p>
<br/>
<p align="center">
  <a href="https://npmjs.com/package/@dragit/editor-plugin-vue"><img src="https://img.shields.io/npm/v/@dragit/editor-plugin-vue.svg" alt="npm package"></a>
  <a href="https://nodejs.org/en/about/releases/"><img src="https://img.shields.io/node/v/@dragit/editor-plugin-vue.svg" alt="node compatility"></a>
  <a href="https://app.circleci.com/pipelines/github/vitejs/vite?branch=main"><img src="https://circleci.com/gh/vitejs/vite/tree/main.svg?style=shield" alt="unix build status"></a>
  <a href="https://ci.appveyor.com/project/yyx990803/vite/branch/main"><img src="https://ci.appveyor.com/api/projects/status/0q4j8062olbcs71l/branch/main?svg=true" alt="windows build status"></a>
  <a href="https://discord.gg/nfX2kYPqvr"><img src="https://img.shields.io/badge/chat-discord-blue?style=flat&logo=discord" alt="discord chat"></a>
</p>
<br/>

# Dragit Email Editor Plugin

> Professional Drag & Drop Email Builder

- 📦 Optimized for speed


# @dragit/editor-plugin-vue

This is a Vue.js wrapper for our [Dragit Email Editor](https://dragit.io/). 

With NPM:
```bash
$ npm install @dragit/editor-plugin-vue
```

With Yarn:
```bash
$ yarn add @dragit/editor-plugin-vue
```


This package comes with one component that you can use:
```vue
<template>
    <dragit-editor-plugin
          :options="options"
          class="border"
          style="width: 100%; height: 800px; position: relative"
    />
</template>

<script>
import DragitEditorPlugin from '@dragit/editor-plugin-vue'

export default {
  components: { DragitEditorPlugin },
  computed: {
      options() {
          return {
              apiKey: 'YOUR_API_KEY',
              language: 'en', // One of ['en', 'cs'],
          }
      }
  }
}
</script>
```

Anytime the options property changes, the editor is going to be destroyed and initialized again.


