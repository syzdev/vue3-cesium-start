<template>
  <div id="cesiumContainer"></div>
</template>

<script setup>
import { onMounted } from 'vue'
import * as Cesium from 'cesium'
import { CesiumIonDefaultAccessToken } from '@/common/js/config'
// 没有CesiumIonDefaultAccessToken则使用官方示例中的Token
Cesium.Ion.defaultAccessToken =
  CesiumIonDefaultAccessToken ||
  'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJqdGkiOiI2YmRiNjM4MC1kMDZkLTQ2NDQtYjQ3My0xZDI4MDU0MGJhZDciLCJpZCI6MzIxMzAsInNjb3BlcyI6WyJhc3IiLCJnYyJdLCJpYXQiOjE1OTY1MjM4NzZ9.A3FBZ6HjKkTsOGnjwWWeO9L10HQ9c-wcF4c3dtTc4gQ'

let viewer = null

const initCesium = () => new Cesium.Viewer('cesiumContainer')

onMounted(() => {
  viewer = initCesium()
})
</script>

<style scoped>
@import 'cesium/widgets.css';
#cesiumContainer {
  height: 100%;
  width: 100%;
  margin: 0;
  padding: 0;
  overflow: hidden;
}
</style>