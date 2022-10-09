<script setup lang="ts">
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
import SimpleCounter from './components/SimpleCounter.vue'
import { VueFrame } from './lib'
const customStyles = `
body {
  background: pink;
  color: black;
}
button {
  border: 2px solid purple;
  border-radius: 4px;
}
`
</script>

<template>
  <main>
    <h1>vue-frame</h1>
    <code>npm i vue-frame</code>
  </main>
  <section>
    <h1>demo</h1>
    <div class="grid">
      <simple-counter width="300" height="200" title="Without iframe" />
      <vue-frame width="300" height="200">
        <simple-counter title="With iframe" />
      </vue-frame>
      <vue-frame width="300" height="200" :inherit-styles="true">
        <simple-counter title="With iframe, inherit styles" />
      </vue-frame>
      <vue-frame width="300" height="200" :stylesheet="customStyles">
        <simple-counter title="With iframe, custom css" />
      </vue-frame>
      <vue-frame width="300" height="200" :inherit-styles="true" :stylesheet="customStyles">
        <simple-counter title="With iframe, inherit styles, custom css" />
      </vue-frame>
    </div>
  </section>
  <footer>
    <ul>
      <li><a href="https://github.com/aryan02420/vue-frame/blob/main/src/App.vue">View source for this page</a></li>
      <li><a href="https://github.com/aryan02420/vue-frame">GitHub</a></li>
    </ul>
  </footer>
</template>

<style scoped>
section {
  margin-top: 120px;
  margin-bottom: 120px;
}
.grid {
  display: flex;
  flex-wrap: wrap;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  gap: 20px;
  max-width: 1000px;
}

.grid>* {
  flex: 1;
}

ul {
  list-style-type: none;
}
</style>
