<script lang="ts" setup>
const isLightMode = ref(false)
const handleClickTorch = () => {
  isLightMode.value = !isLightMode.value
  console.log(isLightMode.value)
}
</script>

<template>
  <div
    class="h-full text-center flex-col justify-center items-center select-none all:transition-400 relative overflow-hidden bg-#000">
    <div class="h-1/2 z-3 flex-col justify-end">
      <div class="text-center flex select-none all:transition-400">
        <div class="text-30 text-#000 p-10 fw600 animate-bounce-alt animate-count-infinite animate-duration-5s">
          Hello World
        </div>
      </div>
    </div>
    <div class="h-1/2">
      <div>
        <MinecraftTorches
          @click="handleClickTorch"
          class="z-2"></MinecraftTorches>
        <div
          class="absolute bg-#fff transition-all duration-1s ease-in-out z-1"
          :class="[
            !isLightMode
              ? 'w-0 h-0 top-[50%] left-[50%] rounded-full bg-#fff'
              : 'w-[300vmax] h-[300vmax] top-[-100vmax] left-[-100vmax] rounded-none bg-#000'
          ]"></div>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
