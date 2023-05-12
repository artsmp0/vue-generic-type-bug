<script setup lang="ts">
import { ref } from 'vue';
import HelloWorld from './components/HelloWorld.vue';

const count = ref(100);
</script>

<template>
  {{ count }}
  <HelloWorld :msg="'hello world'">
    <template #default="{ msg, count }">
      <div>
        {{ msg }}
        {{ count }}
      </div>
    </template>
  </HelloWorld>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
