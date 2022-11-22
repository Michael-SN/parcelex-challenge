<template>
  <form :action="formAction" :id="id" :method="method">
    <slot></slot>
  </form>
</template>

<script>
export default {
  name: "OrganismForm",
  props: ['id', 'formAction', 'method']
}
</script>