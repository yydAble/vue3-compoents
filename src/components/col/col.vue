<template>
  <div :class="{
    [baseClassName]:true,
    [spanClassName]:true
  }">
    <slot v-if="$slots.default" ></slot>
  </div>
</template>
<script setup lang="ts">
  import { prefixName } from '../theme';
  const props = defineProps({
    span:Number
  })

 function getSpan(propSpan:number|undefined):number{
  if(typeof propSpan === 'number'){
    const span:number = Math.ceil(Number(propSpan))
    if(span>=1 && span<=24){
      return span
    }
  }
  return 1
 }
 const baseClassName = `${prefixName}-col`
 const spanClassName = `${baseClassName}-${getSpan(props.span)}`
</script>
