<template>
  <button @click="onClick">点击打开对话框</button>
</template>

<script setup lang="ts">
import { Dialog, Button } from './components';
import test from './example/test.vue';
const onClick = () => {
  const dialog = Dialog.createDialog({
    text: '您好',
    Content: test,
    hideFooter: true,
    onOk: () => {
      dialog.close();
    }
  });
};
</script>
