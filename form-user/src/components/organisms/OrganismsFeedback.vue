<template>
  <div class="absolute inset-0 flex justify-center items-center">
    <div class="overlay absolute inset-0 bg-[#333] opacity-60"></div>
    <div class="relative flex flex-col justify-center items-center bg-violet-600 p-6 text-white rounded-lg">
      <AtomTitle tag="h2" content="Congrats!!" />
      <ul>
        <li v-for="(value, key) in user" class="mb-1">
          <strong class="capitalize">{{ key }}:&nbsp;</strong>{{ value }}
        </li>
      </ul>
      <p class="mt-4"><span class="italic">Status:</span> User has been registred!!</p>
    </div>
  </div>
</template>

<script>
import AtomTitle from '../atoms/AtomTitle.vue';

export default {
  name: "OrganismsFeedback",
  props: ['user'],
  components: { AtomTitle }
}
</script>