<script setup lang="ts">
const props = defineProps<{
  className: string
}>()
const active = ref<boolean>(false)
const fullClassName = computed(() => {
  return `fi ${props.className}`
})
</script>

<template>
  <i
    class="m-2 text-2xl cursor-pointer "
    style="display: inline-block!important;"
    :class="[fullClassName, { 'text-blue-500': active }]" @click="active = !active"
  />
</template>
