<script setup>
    import { VFX } from "@vfx-js/core";
    onMounted(() => {
        const img = document.querySelector('#img');
        const vfx = new VFX();
        vfx.add(img, { shader: "rgbShift" });
    })
</script>
<template>
  <div class="min-h-screen bg-black flex flex-col justify-center items-center text-center">
    <img id="img" src="~/assets/img/kagaribi.png" class="h-40"/>
  </div>
</template>