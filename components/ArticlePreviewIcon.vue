<script lang="ts" setup>
withDefaults(
  defineProps<{
    href: string;
    width?: number;
    height?: number;
  }>(),
  {
    href: "icon-share",
    width: 15,
    height: 13,
  }
);
</script>

<template>
  <svg
    :width="width"
    :height="height"
    :viewBox="`0 0 ${width} ${height}`"
    xmlns="http://www.w3.org/2000/svg"
  >
    <use :href="`/${href}.svg#${href}`" />
  </svg>
</template>
