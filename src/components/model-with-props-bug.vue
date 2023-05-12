<script setup lang="ts" generic="T extends string">
import { computed, ref } from 'vue';

const props = defineProps<{
  msg: T;
}>();

const newMsg = computed<T>(() => props.msg);

defineSlots<{
  default?: (props: { msg: T; count: number }) => any;
}>();

// 当使用 defineModel 时，在模板中访问 msg 报错
const count = defineModel<number>('count', {
  local: true,
  default: 999,
});
</script>

<template>
  <h1>{{ msg }}</h1>

  <div class="card">
    <button type="button" @click="count++">count is {{ count }}</button>
  </div>
  <div>
    <slot name="default" :msg="newMsg" :count="count"> </slot>
  </div>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
