<template>
  <div class="absolute inset-0 flex justify-center items-center" v-if="showFeedback">
    <div class="overlay absolute inset-0 bg-[#333] opacity-60"></div>
    <div class="relative flex flex-col justify-center items-center bg-violet-600 p-6 text-white rounded-lg">
      <AtomTitle tag="h2" content="Success!!" />
      <p>User has been registred!!</p>
    </div>
  </div>
</template>

<script>
import AtomTitle from '../atoms/AtomTitle.vue';

export default {
  name: "OrganismsFeedback",
  props: ['showFeedback'],
  components: { AtomTitle }
}
</script>