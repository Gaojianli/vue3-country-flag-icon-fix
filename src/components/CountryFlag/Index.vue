<template>
  <span
    :class="flagIconClass"
    :title="props.title || props.iso"
    class="flag-icon"
    v-if="props.iso !== ''"
  />
</template>

<script lang="ts" setup>
import "@/assets/scss/country-flag.scss";
import { defineProps, computed } from "vue";

const props = defineProps<{
  iso: string;
  title?: string;
  mode?: "rounded" | "squared";
}>();

const flagIconClass = computed(() => {
  let cls = "";

  cls = "flag-icon-" + props.iso.toLowerCase();

  if (props.mode) {
    cls += " flag-icon-" + props.mode;
  }

  return cls;
});
</script>
