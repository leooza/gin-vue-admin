<template>
  <div>
    <normal-mode v-if="config.side_mode != 'head' || (device === 'mobile'&& config.side_mode == 'head' )" />

    <head-mode v-if="config.side_mode === 'head' && device !== 'mobile'" />
  </div>
</template>

<script setup>
import NormalMode from "./normal.vue"
import HeadMode from "./head.vue"
import { storeToRefs } from "pinia";
import { useAppStore } from "@/pinia";
const appStore = useAppStore();
const { config, device } = storeToRefs(appStore);
</script>
