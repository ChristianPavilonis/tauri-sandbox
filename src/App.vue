
<template>
    <button @click="greet">Greet</button>
</template>

<script setup lang="ts">
import { invoke } from '@tauri-apps/api';

function greet() {
// now we can call our Command!
// Right-click the application background and open the developer tools.
// You will see "Hello, World!" printed in the console!
    invoke('greet', { name: 'World' })
        // `invoke` returns a Promise
        .then((response) => console.log(response));
}
</script>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
