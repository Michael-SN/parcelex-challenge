<template>
  <button type="submit" class="w-full py-3 rounded-lg text-white transition-colors bg-violet-600  hover:bg-violet-700">
    {{ btnText }}
  </button>
</template>

<script>
export default {
  name: "SubmitButton",
  props: ['btnText']
}
</script>