<script setup lang="ts">
import { ref } from "vue";

import { Panel, VueFlow, useVueFlow } from "@vue-flow/core";
import { Background, BackgroundVariant } from "@vue-flow/background";
import { MiniMap } from "@vue-flow/minimap";
import CustomNode from "./CustomNode.vue";
const { nodes, addNodes, addEdges, onConnect, dimensions } = useVueFlow();

// ref
const snapToGrid = ref<boolean>(true);
const snapGrid = ref<any>([20, 20]);

//
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
    type: "custom",
  };

  addNodes([newNode]);
};
</script>

<template>
  <VueFlow :snap-to-grid="snapToGrid" :snap-grid="snapGrid">
    <Background :variant="BackgroundVariant.Dots" />
    <MiniMap />

    <Panel position="top-right">
      <button class="btn" type="button" @click="addRandomNode">node +</button>
      <button class="btn" type="button" @click="addRandomNode">node +</button>
      <button class="btn" type="button" @click="addRandomNode">node +</button>
      <button class="btn" type="button" @click="addRandomNode">node +</button>
    </Panel>

    <template #node-custom="nodeProps">
      <CustomNode :data="nodeProps.data" :label="nodeProps.label" />
    </template>
  </VueFlow>
</template>

<style>
/* import the necessary styles for Vue Flow to work */
@import "@vue-flow/core/dist/style.css";

/* import the default theme, this is optional but generally recommended */
@import "@vue-flow/core/dist/theme-default.css";

/* import default minimap styles */
@import "@vue-flow/minimap/dist/style.css";

/* make sure to include the necessary styles! */
@import "@vue-flow/node-resizer/dist/style.css";
</style>
