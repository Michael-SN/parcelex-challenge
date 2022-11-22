<template>
  <div class="relative mx-auto w-[200px] overflow-hidden border-[2px] border-violet-600 rounded-full">
    <figure class="min-h-[200px] min-w-full">
      <img :src="image" class="absolute w-full h-full" alt="" />
      <figcaption
        class="absolute left-0 right-0 bottom-0 bg-violet-600 text-center text-xs text-white antialiased font-semibold pb-4 pt-2">
        <label for="imageUser" class="cursor-pointer">Change Image</label>
        <input type="file" name="use_img" id="imageUser" @change="changeImage" class="hidden" />
      </figcaption>
    </figure>
  </div>
</template>

<script>
export default {
  name: "AtomInputImage",
  data() {
    return {
      image: 'https://cutewallpaper.org/24/image-placeholder-png/person-image-placeholder-clipart-png-download-no-profile-photo-vector-transparent-png-vhv.png'

    }
  },
  methods: {
    changeImage(e) {
      const file = e.target.files[0]
      this.image = URL.createObjectURL(file)

      console.log(file)
    }
  },
}
</script>