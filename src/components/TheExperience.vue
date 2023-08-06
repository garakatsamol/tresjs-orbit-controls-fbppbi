<script setup lang="ts">
import { ref } from 'vue';
import { Color } from 'three';
import Text3D from './Text3D.vue';

import { useRenderLoop } from '@tresjs/core';
import { OrbitControls, useTweakPane } from '@tresjs/cientos';

const colorTeal = new Color('teal');

const meshPosition = [0, 3, 0];

const { onLoop } = useRenderLoop();

const sphereRef = ref(null);

// Orbit controls by extending

/* import { OrbitControls } from 'three/examples/jsm/controls/OrbitControls'
import { useTres, useCatalogue } from '/@/core'

const { extend } = useCatalogue()

extend({ OrbitControls }) */
</script>

<template>
  <TresCanvas
    clear-color="#82DBC5"
    shadows
    alpha
    window-size
    power-preference="high-performance"
    preserve-drawing-buffer
    physically-correct-lights
  >
    <OrbitControls />
    <TresPerspectiveCamera
      :position="[1, 2, 5]"
      :fov="45"
      :aspect="1"
      :near="0.1"
      :far="1000"
    />
    <TresScene>
      <!--  <TresOrbitControls v-if="state.renderer" :args="[state.camera, state.renderer?.domElement]" /> -->
      <Text3D />
      <TresDirectionalLight :position="[0, 2, 4]" :intensity="2" cast-shadow />
    </TresScene>
  </TresCanvas>
</template>
