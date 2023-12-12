<script lang="ts" setup>
import { computed } from "vue";

import { Handle, Position } from "@vue-flow/core";
import { NodeResizer } from "@vue-flow/node-resizer";

// make sure to include the necessary styles!
//import "@vue-flow/node-resizer/dist/style.css";

defineProps(["label"]);

const sourceHandleStyleA = computed(() => ({
  backgroundColor: "#F00",
  top: "50px",
}));
</script>

<template>
  <NodeResizer
    :min-width="100"
    :min-height="50"
    :style="sourceHandleStyleA"
    color="#F00"
    handleClassName="handleClassName"
  />

  <Handle type="target" :position="Position.Left" />
  <div style="padding: 10px">{{ label }}</div>
  <Handle type="source" :position="Position.Right" />
</template>

<style scoped>
.handleClassName {
  width: 200px;
}
</style>
