<template>
  <div id="app">
    <CesiumScene />
  </div>
</template>

<script setup>
import CesiumScene from './components/CesiumScene.vue'
</script>

<style>
html, body, #app {
  height: 100%;
  width: 100%;
  margin: 0;
  padding: 0;
  overflow: hidden;
}
</style>