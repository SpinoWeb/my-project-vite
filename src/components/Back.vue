<script setup lang="ts">
//import { ref } from "vue";

import { Panel, VueFlow, useVueFlow } from "@vue-flow/core";
import { Background, BackgroundVariant } from "@vue-flow/background";
import { MiniMap } from "@vue-flow/minimap";

const { nodes, addNodes, addEdges, onConnect, dimensions } = useVueFlow();

onConnect((params) => addEdges(params));

const addRandomNode = () => {
  const nodeId = (nodes.value.length + 1).toString();

  const newNode = {
    id: nodeId,
    label: `Node: ${nodeId}`,
    position: {
      x: Math.random() * dimensions.value.width,
      y: Math.random() * dimensions.value.height,
    },
  };

  addNodes([newNode]);
};
</script>

<template>
  <VueFlow :snap-to-grid="true">
    <MiniMap />

    <Background :variant="BackgroundVariant.Points" />

    <Panel position="top-right">
      <button class="btn" type="button" @click="addRandomNode">add node</button>
    </Panel>
  </VueFlow>
</template>

<style>
/* import the necessary styles for Vue Flow to work */
@import "@vue-flow/core/dist/style.css";

/* import the default theme, this is optional but generally recommended */
@import "@vue-flow/core/dist/theme-default.css";

/* import default minimap styles */
@import "@vue-flow/minimap/dist/style.css";
</style>
