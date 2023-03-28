<script setup lang="ts">
import { onMounted } from 'vue';
import  OpenSeadragon  from 'openseadragon';

onMounted(()=>{
  initOpenSeadragon()
})

const getImgUrl = (name: string) => {
  return new URL('../assets/' + name, import.meta.url).href
}

const initOpenSeadragon = ()=>{
  OpenSeadragon({
    id: "openseadragon1", //body中挂载的id
    prefixUrl: "https://openseadragon.github.io/openseadragon/images/",
    tileSources: getImgUrl('snt.dzi'),
    showNavigator:true,
      // Initial rotation angle
      degrees: 0,
      // Show rotation buttons
      showRotationControl: true,
      // Enable touch rotation on tactile devices
      gestureSettingsTouch: <any>{
          pinchRotate: true
      }
  })
}

</script>

<template>
  <div id="openseadragon1"></div>
</template>

<style scoped>
#openseadragon1{
  width: 100%;
  height: 800px;
}
</style>
