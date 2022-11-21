<template>
  <component :is="tag" class="mb-8 text-3xl tracking-wider text-center">{{ content }}</component>
</template>

<script>
export default {
  name: "AtomTitle",
  props: ['tag', 'content']
}
</script>