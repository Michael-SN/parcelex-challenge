<template>
  <div class="flex flex-col mb-4">
    <label :for="forInput" class="mb-3 font-semibold tracking-wide">{{ legend ? legend + ':' : '' }}</label>
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: 'MoleculeFormGroup',
  props: ['legend', 'forInput']
}
</script>