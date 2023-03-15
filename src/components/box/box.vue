<template>
  <div :class="{[baseClassName]:true}">
    <slot v-if="$slots.default"></slot>
  </div>
</template>

<script setup ts>
  import {prefixName} from './../theme/index'
  const baseClassName = `${prefixName}-box`
</script>
