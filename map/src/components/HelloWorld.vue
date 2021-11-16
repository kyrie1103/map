<template>
  <el-alert>11</el-alert>
  {{ name }}
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";

export default defineComponent({
  setup() {
    const name = ref(1);

    return {
      name,
    };
  },
});
</script>
