<template>
  <input
    class="rounded-lg border border-gray-400 px-4 py-3 transition-colors focus:border focus:border-violet-500 focus:outline-0"
    :type="typeInput" :name="nameInput" :id="idInput" :value="value" :required="required" @input="updateValue" />
</template>

<script>
export default {
  name: "AtomInputText",
  props: ['typeInput', 'idInput', 'nameInput', 'required', 'value'],
  methods: {
    updateValue(event) {
      const value = event.target.value
      this.$emit('update:value', value)
    },

  },
}
</script>